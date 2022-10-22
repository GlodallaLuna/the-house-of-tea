<script setup>
import { RouterLink, RouterView } from 'vue-router';
import { ref, computed } from 'vue'

const props = defineProps({
    // Changes style to transparent if isHome is true (this is done in computed background)
    page: String
})

// Reactive state variables
const isOpen = ref(false);

// Opening and closing the mobile navbar
const openCloseClass = computed(() => isOpen.value ? 'open' : 'closed')    

//for changing the hamburger to X
const icon = computed(() => isOpen.value ? 'fa-solid fa-square-xmark' : 'fa-solid fa-bars')

// Make the navbar transparent on the home page
const background = computed(() => props.page === 'home' ? '' : 'nav-cinnamon') 

//logic for the event listener to open and close navbar
const navSwitcher = () => isOpen.value = !isOpen.value

//to underline the navbar link that is the same as the current page
const underline = (targetPage) => targetPage === props.page ? 'underlined' : ''

</script>

<template>

    <nav :class="background">
        <div class="logo"><a href=""><img src="@/assets/images/logo.svg" alt=""></a></div>
        <button @click="navSwitcher" class="toggle" aria-controls="nav-control" area-expanded="false">
            <font-awesome-icon class="hamburger" :icon="icon" />
        </button>
        <div class="primary-nav" :class="openCloseClass">
            <div></div>
            <div class="primary-nav__links">
                <ul class="nav__links" id="nav-control">
                    <li>
                        <router-link to="/" class="nav__link" :class="underline('home')">Home</router-link>
                    </li>
                    <li>
                        <router-link to="/shop" class="nav__link" :class="underline('shop')">Shop</router-link>
                    </li>
                    <li><a class="nav__link" href="">Contact</a></li>
                </ul>
            </div>

            <div class="container__cart">
                <font-awesome-icon class="cart" icon="fa-solid fa-bag-shopping" />
                : &euro;0
            </div>
        </div>

    </nav>

</template>


<style>
nav {
    display: flex;
    padding: 1rem 1.5rem .7rem 1.5rem;

}

.nav-cinnamon {
    background-color: var(--clr-cinnamon);
}

.toggle {
    visibility: hidden;
    z-index: 1000;
}

.primary-nav {
    display: flex;
    width: 100%;
    justify-content: space-between;

}



.nav__links {
    display: flex;
}

.nav__link {
    font-family: var(--font-cinzel);
    padding: 0 2.5rem;
    font-size: 1.2rem;
}

.underlined {
    text-decoration: underline;
}

.icon,
.container__cart {
    color: white;
    font-family: var(--font-cinzel);
    font-size: 1.2rem;
}

.cart {
    font-size: 1.3rem;
}

@media screen and (max-width: 43.125em) {
    .toggle {
        visibility: visible;
        position: absolute;
        background-color: transparent;
        border: none;
        aspect-ratio: 1;
        top: 1rem;
        right: 1.5rem;
    }

    .hamburger {
        font-size: 1.8rem;
        color: var(--clr-primary-white);
        z-index: 1000;
    }

    .primary-nav {
        position: fixed;
        padding: min(10vh, 5rem) 2em;
        inset: 0 0 0 0;
        background-color: var(--clr-cinnamon);
        justify-content: start;
        z-index: 999;
    }

    .closed {
        transform: translateX(100%);
    }

    .open {
        transform: translateX(0%);
    }



    .primary-nav__links,
    .primary-nav,
    .nav__links {
        display: flex;
        flex-direction: column;
    }

    .nav__links {
        padding: 0;
    }

    .nav__links>li {
        padding-top: 1.5rem;
    }

    .cart,
    .nav__link,
    .container__icon {
        font-size: 1.5rem;
    }

    .container__cart {
        padding: 2rem 2.5rem;
        font-size: 1.5rem;

    }
}
</style>