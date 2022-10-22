<script setup>
import Navbar from '../components/Navbar.vue'
import Footer from '../components/Footer.vue'
import { ref, computed } from 'vue'

const props = defineProps({
    stock: Array
})

const newArrivals = computed(() => {
    
    // Get all the new arrivals
    const newArrivals = props.stock.filter((tea) => {
        return tea["new-arrival"] === "true"
    })
    
    // Take the first three
    const threeArrivals = newArrivals.slice(0,3)
    return threeArrivals
})

</script>

<template>

    <header class="home-header">
        <Navbar page="home" />
        <div class="header__content">
            <p class="subtitle">Organic Tea Shop</p>
            <h1 class="title">The House of Tea</h1>
            <router-link to="/shop" class="header__button">View Shop</router-link>
        </div>
    </header>

    <main>
        <div class="section section__light content-wrapper">
            <div>
                <h2 class="title--cinnamon">exquisite tea from six countries in the world</h2>
                <p>We have over 20 years of experience travelling all across Asia selecting the highest quality tea.
                    Our tea is sourced directly from growers and small producers of less than 15 acres.
                    We meet our farmers from a place of equity, respect and community, and put low-intervention farming
                    methods and minimal processing of the leaves at the heart of what we do. We belive that by supporting
                    ethical producers, we can do our part to move the global tea market toward a more sustainable future.
                </p>
            </div>
            <div class="home__img"><img
                    src="../assets/images/alisher-sharip-mumpl9-D7Uc-unsplash.jpg"
                    alt="tea leaves and a teaset"></div>
        </div>

        <div class="section section__dark">
            <div class="content-wrapper">
                <div class="home__img home__img--modified"><img
                        src="../assets/images/max-griss-X3Sinj7qZGc-unsplash.jpg"
                        alt="transparent teapot with with Jasmine, Lily Rose inside"></div>
                <div>
                    <h2 class="title--orange">a selection of herbal teas and botanicals</h2>
                    <p>Herbal teas are becoming more and more popular and it's easy to see why. With delicious flavors and
                        possible health benefits, herbal teas are a great choice for any tea enthusiast or rookie.
                        We carefully blend and custom craft the finest herbal teas and botanicals for every need.
                        If you are not sure which one is the best blend for you, you can ask our exprets and we will help you
                        find the perfect beverage.
                    </p>
                </div>
                <div>
                </div>
            </div>
        </div>

        <div class="section section__light">
            <h2 class="title--cinnamon centered">New Arrivals</h2>
            <p class="centered">Our Seasonal Selection</p>
            <div class="content-wrapper--arrivals">                
                <div v-for="tea in newArrivals">
                    <div class="img--arrivals"><img :src="tea.image"></div>
                    <h3 class="title--arrivals"><a href="">{{tea.name}}</a></h3>
                </div>
            </div>
            <div class="wrapper__button"><router-link to="/shop" class="arrivals__button">Browse Teas</router-link></div>
        </div>
    </main>

    <Footer />
</template>

<style scoped>
.home-header {
    background-image: url("../assets/images/dmitry-vechorko-WBg21rPlHeE-unsplash.jpg");
    color: var(--clr-primary-white);
    background-position: top;
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 27rem;
}

.header__content {
    display: grid;
    justify-items: center;
    align-items: center;
    margin-top: 20%;
    padding: 0 1rem;
    text-align: center;
}

.title {
    font-size: 2.4rem;
    line-height: 1.2;
}

.subtitle,
.header__button {
    font-family: var(--font-cinzel);
}

.header__button,
.arrivals__button {
    font-family: var(--font-cinzel);
    padding: .4rem .8rem;
    margin-top: 1rem;
    border: 0;
    background-color: var(--clr-orange);
    letter-spacing: 1.6px
}

.arrivals__button {
    background-color: var(--clr-primary-black);
    color: var(--clr-primary-white);
}
.wrapper__button {
    margin-top: 1rem;
    display: flex;
    justify-content: center;
    width: 100%;
    
}

.header__button:hover,
.arrivals__button:hover {
    background-color: var(--clr-cinnamon);
    text-decoration: none;
}

/*sections styles */
.section {
    padding-top: 1.5rem;
    padding-bottom: 2rem;
}

.title--cinnamon {
    color: var(--clr-cinnamon);
}

.title--orange {
    color: var(--clr-orange);
}

.title--cinnamon,
.title--orange {
    margin: .5rem 0;
}

.centered {
    text-align: center;
}

.home__img,
.img--arrivals {
    margin: 1.3rem;
}

.section__dark {
    background-color: var(--clr-primary-black);
    color: var(--clr-primary-white);
}

.home__img--modified {
    display: none;
}

.title--arrivals {
    text-align: center;
    color: var(--clr-cinnamon);
}
.title--arrivals>a {
    color: var(--clr-cinnamon);
}


.img--arrivals>img {
    max-width: 250px;
    max-height: 250px;
    margin: 0 auto;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 2px 5px -1px, rgba(0, 0, 0, 0.3) 0px 1px 3px -1px;
}

@media screen and (min-width: 37.5em) {
    /*sections styles */
    .content-wrapper,
    .content-wrapper--arrivals {
        max-width: 62.5rem;
        margin: 0 auto;
    }
    .content-wrapper {
        display: grid;
        grid-template-columns: 1fr 1fr;
        
    }

    .content-wrapper--arrivals {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
    }
    
    .home__img--modified {
        display: block;
    }

    
}

@media screen and (min-width: 50.9em) {
    .home-header {
        min-height: 38rem;
        background-position: center;
    }

    .header__content {
        margin-top: 13%;
        letter-spacing: 1.5px;
    }

    .title {
        font-size: 4rem;
    }

    .subtitle,
    .header__button,
    .arrivals__button {
        font-size: 1.25rem;

    }

    

    

}

@media screen and (min-width: 70em) {
    .home-header {
        min-height: 48rem;
    }
}
</style>