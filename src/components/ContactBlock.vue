<template>
    <div class="contactBlock container">
            <div class="contactInfo">
                <h2 class="blockTitle">
                    Contact us!
                </h2>
                <p class="subscription">
                    The support staff and customer service are available
                    to help you with any questions or needs you might
                    have. Just drop us a line.
                </p>
                <p class="secondary">
                    This site is owned and operated by Kode Tech Solutions LTD
                </p>
                <div class="contactElement">
                    <span class="contactTitle">
                        Phone
                    </span>
                    <span class="contactBody">
                        442038857261
                    </span>
                </div>
                <div class="contactElement">
                    <span class="contactTitle">
                        Email
                    </span>
                    <span class="contactBody">
                        help@google.com
                    </span>
                </div>
                <div class="contactElement">
                    <span class="contactTitle">
                        Address
                    </span>
                    <span class="contactBody">
                        Trust Company Complex, Ajeltake Road, Ajeltake Island,
                        Majuro, Republic of the Marshall Islands, MH 96960
                    </span>
                </div>
            </div>
            <ContactForm />
        </div>
</template>

<script>
import ContactForm from './ContactForm'
export default {
    components: {
        ContactForm
    }
}
</script>

<style scoped>
.contactBlock{
    padding: 120px;
    background: #F0F0FF;
    display: flex;
    justify-content: space-between;
}
.blockTitle{
     background: none;
}
.subscription{
    font-family: 'Montserrat', sans-serif;
    max-width: 40ch;
    margin: 32px 0 48px 0;
}
.secondary{
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 27px;
    margin: 24px 0;
    max-width: 100%;
}
.contactElement{
    display: flex;
    flex-direction: column;
    margin: 16px 0;
}
span{
    margin: 4px 0;
}
.contactBody{
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 27px;
    color: #4F4F4F;
    max-width: 42ch;
}
@media screen and (max-width: 768px) {
    .blockTitle{
        text-align: center;
        margin: auto;
    }
    .contactBlock{
        flex-direction: column;
        padding: 48px 130px;
    }
    .subscription{
    max-width: 44ch;
    line-height: 30px;
    }
}
@media screen and (max-width: 480px) {
    .contactBlock{
        padding: 48px 20px;
    }
    .blockTitle{
        text-align: start;
    }
}
</style>