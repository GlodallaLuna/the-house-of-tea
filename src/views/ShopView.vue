<script setup>
import Navbar from '../components/Navbar.vue'
import Menu from '../components/Menu.vue'
import Footer from '../components/Footer.vue'
</script>

<template>

    <Navbar page="shop" />
    <Menu />
    <!-- div to heandle the header and grid component in mobile and desktop version -->
    <div>
        <header class="header--shop">
            <h2 class="title--shop"> Categories: New Arrivals</h2>
            <div class="searchbar">
                <input type="text" class="search__input" aria-label="search" placeholder="search...">
                <button class="search__submit" aria-label="submit"><font-awesome-icon class="submit__icon" icon="fa-solid fa-magnifying-glass" /></button>
            </div>
        </header>
        <!-- here goes the grid component with cards -->
    </div>
    <Footer />

</template>

<style scoped>
h2 {
    padding: 0 0 .5rem 0;
    border-bottom: 1px solid var(--clr-gray-100);
}

.searchbar {
    display: flex;
    margin-top: 1rem;
    border: 1px solid var(--clr-gray-100);
    box-shadow: var(--box-shadow);
    border-radius: 50px;
    padding: .3rem .5rem;
}

.search__input {
    width: 100%;
    border: none;
}

.search__input:focus {
    outline: 0;
}

::placeholder  {
    letter-spacing: 1px;
    font-size: 1rem;
}

.search__submit {
    border: none;
    background-color: var(--clr-primary-white);
    cursor: pointer;
}

.submit__icon {
    font-size: 1.3rem;
    color: var(--clr-gray-200);
    
}


@media screen and (min-width: 45em) {
    .header--shop {
        display: flex;
        justify-content: space-between;
        width: 100%;
        max-width: 62.5rem;
    }

    h2 {
        border: none;
        padding: 0;
    }

    .searchbar {
        margin-top: 0;
        max-width: 15rem;
        
    }
}


    

</style>