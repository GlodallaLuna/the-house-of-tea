<script>
</script>

<template>
    <footer>
        
        <div class="footer__container">
            <div class="footer__list">
                <h3>Get Help</h3>
                <ul>
                    <li>Delivery Methods</li>
                    <li>Payments Methods</li>
                    <li>Return and Exchange</li>
                </ul>
            </div>
            <div class="footer__list">
                <h3>Support</h3>
                <ul>
                    <li>Pricavy Policy</li>
                    <li>Send an Opinion</li>
                </ul>
            </div>
            
            
            <div class="footer__list">
                <h3>About Us</h3>
                <ul>
                    <li>Our Philosophy</li>
                    <li>Contact</li>
                </ul>
            </div>
            <div class="footer__list">
                <h3>Contact</h3>
                <ul>
                    <li>+22 48564857</li>
                    <li>teahouse@mail.com</li>
                </ul>
            </div>
            
            
            <div class="footer__list">
                <h3>Follow Us</h3>
                <ul>
                    <li>Facebook</li>
                    <li>Instagram</li>
                </ul>
            </div>
        </div>
        <p class="footer__paragraph">&copy2022 | Designed and Built by Gloria Mancini & Niall Byrnes</p>
        
    </footer>
</template>


<style>
    footer {
        background-color: var(--clr-cinnamon);
        color: var(--clr-primary-white);
        width: 100%;
        display: grid;
        padding: 3rem 1rem 1rem 1rem;
        font-size: .8rem;
        position: sticky;
        top: 100%;
    }

    .footer__container {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 2.5em;
        margin: 0 auto;
        
    }
    

    .footer__list>ul {
        padding-left: 0;
        
    }

    .footer__list>ul>li {
        padding-top: .5rem;
    }

    .footer__paragraph {
        font-size: .8rem;
        margin-top: 2.5rem;
        text-align: center;
    }


    @media screen and (min-width: 750px) {
        .footer {
            padding: 1.5rem 1rem;
        }

        .footer__container { 
        grid-auto-flow: column;
       }
    }


    @media screen and (min-width: 540px) {
       .footer__container { 
        grid-template-columns: repeat(3, 1fr);
       }

    }

   


</style>