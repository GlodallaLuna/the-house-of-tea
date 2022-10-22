<script>
export default {
    data () {
        return {
            isOpen: false,
        }
    },
    
    methods: {
        //logic for the event listener to open and close navbar
        dropdownSwitcher () {
            this.isOpen = !this.isOpen
        }
        
    },

    computed: {

        // Opening and closing the mobile navbar
        openCloseClass() {
            return this.isOpen ? 'open' : 'closed'
        }

    }
}
</script>

<template>
    <div class="menu">
        <div class="dropdown">
            <button @click="dropdownSwitcher" class="menu__button">
                <h3 class="menu__title">Categories</h3>
                <font-awesome-icon class="arrow-down" icon="fa-solid fa-chevron-down" />
            </button>
            <div class="dropdown-menu" :class="openCloseClass">
                <ul class="menu__links" >
                    <li><a class="menu__link" href="#">All</a></li>
                    <li><a class="menu__link" href="#">Black Tea</a></li>
                    <li><a class="menu__link" href="#">Green Tea</a></li>
                    <li><a class="menu__link disabled" href="#">White Tea</a></li>
                    <li><a class="menu__link disabled" href="#">Matcha</a></li>
                    <li><a class="menu__link" href="#">Herbal Tea</a></li>
                    <li><a class="menu__link disabled" href="#">Rooibos</a></li>
                    <li><a class="menu__link" href="#">Best Sellers </a><font-awesome-icon icon="fa-regular fa-star"/></li>
                    <li><a class="menu__link" href="#">New Arrivals</a></li>
                </ul>

                <div class="menu__sorted-price">
                    <h3 class="menu__title">Sorted by Price</h3>
                    <div class="menu__checkbox"><label><input type="radio" name="radio"/> Low to High </label></div>
                    <div class="menu__checkbox"><label><input type="radio" name="radio"/> High to Low </label></div>
                </div>
            </div>
        </div>
        
    </div>
</template>

<style scoped>
.menu {
    margin: 1.3rem;
    position: relative;
}
.dropdown,
.dropdown-menu{
    border: 1px solid var(--clr-gray-100);
    background-color: var(--clr-primary-white);
    box-shadow: var(--box-shadow);
    padding: 1rem;
} 

.dropdown {
    padding: .3rem 1rem;
}

.dropdown-menu {
    position: absolute;
    left: 0;
    width: 100%;
    border-top: none;
    z-index: 998;
    
}

.menu__links {
    list-style: disc;
    padding-left: 1.2rem;
}

.menu__links>li {
    margin-left: 1rem;
    padding: .5rem 0;
}

.menu__link {
    color: var(--clr-primary-black);
}

.menu__link:hover {
    text-decoration: underline;
}
.menu__title {
    font-family: var(--font-cinzel);
    font-size: 1.4rem;
    color: var(--clr-primary-black);
}

.menu__button {
    background-color: var(--clr-primary-white);
    border: none;
    cursor: pointer;
    display: flex;
    width: 100%;
    justify-content: space-between;
    align-items: center;
}

.arrow-down {
    font-size: 1.35rem;
    color: var(--clr-gray-200);
}

/* sorted price and radio button styles  */

.menu__sorted-price {
    /* padding: 1.5rem 1.2rem 1rem 1.2rem; */
    padding-top: 1.2rem;
}

.menu__checkbox {
    margin-left: 1rem;
    padding: .2rem;
}

label {
    display: flex;
    align-items: center;
    gap: .7rem;
}


.open {
    opacity: 1;
    pointer-events: auto; 
}

.closed {
    opacity: 0;
    pointer-events: none;
}

.disabled {
    color: var(--clr-gray-200);
    /* pointer-events: none; */
    cursor: not-allowed;
}

@media screen and (min-width: 63.75em) {

    .dropdown{
        margin-top: 4rem;
        padding: 1.2rem 1rem;
    }
    .dropdown-menu {
        opacity: 1;
        pointer-events: auto; 
        position: static;
        box-shadow: none;
        border: none;
        padding: 1rem .5rem;
        
    }

    .arrow-down{
        display: none;
    }
}




</style>