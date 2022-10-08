<script>
</script>

<template>
    <footer>
        <div class="footer__row">
            <div class="footer__list">
                <h3>Get Help</h3>
                <ul>
                    <li>Delivery methods</li>
                    <li>Payments methods</li>
                    <li>Return and exchange</li>
                </ul>
            </div>

            <div class="footer__list">
                <h3>Support</h3>
                <ul>
                    <li>Pricavy Policy</li>
                    <li>Send an Opinion</li>
                </ul>
            </div>
        </div>

        <div class="footer__row">
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
        </div>
        <div class="footer__row">
            <div class="footer__list">
                <h3>Follow Us</h3>
                <ul>
                    <li>Facebook</li>
                    <li>Instagram</li>
                </ul>
            </div>
        </div>
    </footer>
</template>


<style>
    footer {
        background-color: var(--clr-cinnamon);
        color: var(--clr-primary-white);
        padding: .7rem;
        font-size: .7rem;
    }

    .footer__row {
        display: flex;
        width: 100%;
        justify-content: space-between; 
    }

    .footer__list {
        width: 160px;
        padding: 1rem;
        
    }

    .footer__list>ul {
        padding: 0;
        margin-top: .8rem;
    }


    @media screen and (min-width: 700px) {
        footer {
            display: flex;
            width: 100%;
            
        }

    }


</style>