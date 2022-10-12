<script>
export default {
    
    data () {
        return {
            isOpen: false,
            isHome: true,
        }
    },
    
    methods: {
        navSwitcher () {
            this.isOpen = !this.isOpen
        }
        
    },

    computed: {
        openCloseClass () {
            return this.isOpen ? 'open' : 'closed'
        },

        icon () {
            return this.isOpen ? 'fa-solid fa-circle-xmark' : 'fa-solid fa-bars'
        },

        background () {
            return this.isHome ? '' : 'nav-cinnamon'
        }
    }
}
</script>

<template>

<nav :class="background">
    <div class="logo"><a href=""><img src="@/assets/images/logo.svg" alt=""></a></div>
    <button @click="navSwitcher" class="toggle" aria-controls="nav-control" area-expanded="false"><font-awesome-icon class="hamburger" :icon="icon" /></button>
    <div class="primary-nav" :class="openCloseClass">
        <div></div>
        <div class="primary-nav__links">
            <ul class="nav__links" id="nav-control">
                <li><a class="nav__link" href="">Home</a></li>
                <li><a class="nav__link" href="">Shop</a></li>
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
body {
    background-color: black;
}

nav {
    display: flex;
    padding: .7rem 1.5rem;
    
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

.icon,
.container__cart {
    color: white;
    font-family: var(--font-cinzel);
    
}

.cart {
  font-size: 1.3rem;
}

@media screen and (max-width: 35em) {
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
    .container__icon{
        font-size: 1.5rem; 
    }

    .container__cart{
        padding: 2rem  2.5rem;
        
    }
}


</style>