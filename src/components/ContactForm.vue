<template>
    <form
        action="submit"
        class="contactForm">
        <input
            v-model="name"
            type="text"
            placeholder="Name"/>
        <span
            class="errorMessage"
            v-if="errors.errorName">
            {{errors.errorName}}
        </span>
        <input
            v-model="email"
            type="email"
            placeholder="Email"/>
        <span
            class="errorMessage"
            v-if="errors.errorEmail">
            {{errors.errorEmail}}
        </span>
        <textarea
            v-model="message"
            placeholder="Message">
        </textarea>
        <Button
        @click="submitHandler"
            :text="'send'"
            />
    </form>
</template>

<script>
import Button from './Button'
export default {
    data: () => ({
        errors: {
            errorName: null,
            errorEmail: null
        },
        name: null,
        email: null,
        message: null
    }),
    components: {
        Button
    },
    methods: {
        submitHandler(event) {
            this.errors.errorName= null
            this.errors.errorEmail= null
            if (!this.name) {
                this.errors.errorName = "Empty name."
            }
            if (!this.email) {
                this.errors.errorEmail = "Empty email."
            } else if (!this.validEmail(this.email)) {
                this.errors.errorEmail = "Incorrect email type."
            }
            if(!this.errors.errorEmail || !this.errors.errorEmail){
                alert("Thank you, " + this.name + "! We will write you on " + this.email + " soon.")
                this.name = ""
                this.email = ""
                this.message = ""
            } 
            event.preventDefault()  
        },
        validEmail (email) {
            var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
            return re.test(email)
        }
    }
}
</script>

<style scoped>
.contactForm{    
    width: 585px;
    max-width: 585px;
    height: 471px;
    background-color: #fff;
    border: 2px solid #6248FF;
    border-radius: 20px;
    display: flex;
    flex-direction: column;
    padding: 80px;
}
input{
    border: 1px solid #E0E0E0;
    border-radius: 3px;
    padding: 7px 16px;
    margin-bottom: 24px;
    color: #828282;
}
textarea{
    border: 1px solid #E0E0E0;
    border-radius: 3px;
    padding: 7px 16px;
    margin-bottom: 12px;
    color: #828282;
    resize: none;
}
input:focus{
    border: 1px solid #828282;   
}
textarea:focus{
    border: 1px solid #828282;
}
button{
    margin: auto;
}
.errorMessage{
    margin-top: -20px;
    margin-bottom: 4px;
    font-size: 14px;
    color: #EB5757;
}
@media screen and (max-width: 768px) {
    .contactForm{
        width: auto;
    }
    textarea{
    margin-bottom: 22px;
    }   
}
@media screen and (max-width: 320px) {
    .contactForm{
        padding: 48px 16px;
        height: auto;
    }
    textarea{
    margin-bottom: 48px;
    } 
}
</style>