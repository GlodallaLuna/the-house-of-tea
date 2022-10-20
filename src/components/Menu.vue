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
            <div class="dropdown-menu" :class="openCloseClass">content</div>
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
} 

.dropdown {
    padding: .2rem .4rem;
}

.dropdown-menu {
    position: absolute;
    left: 0;
    width: 100%;
    border-top: none;
    padding: .2rem 1rem;
    font-size: 1.2rem;
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



.open {
    opacity: 1;
    pointer-events: auto; 
}

.closed {
    opacity: 0;
    pointer-events: none;
}

@media screen and (min-width: 50.9em) {
    .dropdown-menu {
        opacity: 1;
        pointer-events: auto; 
    }

    .arrow-down{
        display: none;
    }
}




</style>