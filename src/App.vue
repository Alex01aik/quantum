<template>
  <Header />
  <main>
    <Topic />
    <StepsBlock 
        :steps="steps"/>
    <CommentsBlock
        :comments="comments"/>
    <QuestionsBlock
        :questions="questions"/>
    <ContactBlock />
  </main>
  <Footer />
</template>

<script>
import Header from '@/components/Header'
import Footer from '@/components/Footer'
import Topic from '@/components/Topic'
import StepsBlock from '@/components/StepsBlock'
import CommentsBlock from '@/components/CommentsBlock'
import QuestionsBlock from '@/components/QuestionsBlock'
import ContactBlock from '@/components/ContactBlock'
export default {
  name: 'App',
  data: () => ({
    steps: [
            {
                number: "01.",
                title: "Register",
                description: "Complete the simple registration to get your trading credentials."
            },
            {
                number: "02.",
                title: "Verification",
                description: "Big Invest is required to verify your identity, upload your documents quickly and get approved in minutes."
            },
            {
                number: "03.",
                title: "Deposit funds",
                description: "Big Invest accepts credit cards and bank wires. Just use the secure deposit form and follow the steps."
            },
            {
                number: "04.",
                title: "Start Trading",
                description: "Once your deposit has been credited, you can begin trading instantly. In no time you will see profits rolling into your account."
            }
        ],
    comments: [
        {
            fullname: "Alberto Abello",
            position: "Director of Growth",
            commentBody: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
            date: "01 / 04",
            portret: "portret.jpg"
        },
        {
            fullname: "Alberto Abello",
            position: "Main Director of Growth",
            commentBody: "This magical product actually works! It has radically changed the way we build our audiences. Increasing new customer sales by 6x in our most mature market.",
            date: "02 / 04",
            portret: "portret.jpg"
        },
    ],
    questions: [
        {
            title: "How do I change my details?",
            description: "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!"
        },
        {
            title: "What platforms will I be able to use?",
            description: "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!"
        },
        {
            title: "How do I change my details?",
            description: "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!"
        },
        {
            title: "How do I change my details?",
            description: "We provide only the best trading software. The trading terminal MetaTrader4 is the most popular and convenient platform for access to global exchanges. You can work anywhere. All you need is the Internet because the necessary trading tools are already collected in one place and are available in a couple of clicks. Use only the best and develop with us!"
        },
    ]
  }),
  components: {
    Header,
    Footer,
    Topic,
    StepsBlock,
    CommentsBlock,
    QuestionsBlock,
    ContactBlock
  }
}
</script>

<style>
@font-face {
    font-family: 'Montserrat';
    src: url("./assets/fonts/Montserrat-Regular.ttf") format('truetype');   
}
@font-face{
    font-family: 'Museo Sans Cyrl';
    src: url("./assets/fonts/MuseoSansCyrl-500.ttf") format('truetype');
}
*{
    box-sizing: border-box;
}
*:focus {
    outline: none;
}
body{
    margin: 0;
    width: 100%;
    font-family: 'Museo Sans Cyrl', sans-serif;
    color: #333333;   
}
a{
    text-decoration: none;
    color: #333333;
}

h1, h2, h3, h4, h5, h6 {
    margin: 0;
}
.container{
    padding-left: 120px;
    padding-right: 120px;
}
.logo{
    width: 45px;
    height: 16px;
    font-weight: 700;
    text-transform: uppercase;
}
.blockTitle{
    font-size: 56px;
    line-height: 66px;
    max-width: 12.5ch;
    background: url('./assets/graybackground.png');
    background-position: left bottom;
    background-repeat: no-repeat;
}
@media screen and (max-width: 768px) {
    .container{
        padding-left: 40px;
        padding-right: 40px;
    }
}
@media screen and (max-width: 320px) {
    .container{
        padding-left: 20px;
        padding-right: 20px;
    }
    .blockTitle{
        font-size: 40px;
        line-height: 44px;
    }
}
</style>
