<template>
    <div class="topic">
            <div class="topBlockText">
                <h1 class="topTitle">
                    Trade everywhere. Invest here!
                </h1>
                <p class="topSubtitle">
                    We provide only the best trading software.
                    The trading terminal MetaTrader4 is the most popular
                    and convenient platform for access to global exchanges.
                    You can work anywhere.
                </p>
                <Button
                    :text="'start trading'"/>
            </div>
            <img src="../assets/diagramm.png" alt="diagramm" />
        </div>
</template>

<script>
import Button from '@/components/Button'
export default {
    components: {
        Button
    }
}
</script>

<style scoped>
.topic{
    background-color: #F0F0FF;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 100px 120px;
}
.topTitle{
    font-size: 64px;
    line-height: 72px;
    max-width: 18ch;
}
.topSubtitle{
    font-family: 'Montserrat', sans-serif;
    font-size: 18px;
    line-height: 30px;
    margin-top: 32px;
    margin-bottom: 16px;
    max-width: 37ch;
}

@media screen and (max-width: 768px) {
    .topic{
        padding: 40px;
        flex-direction: column;
        text-align: center;
    }
    .topTitle{
        margin-bottom: 32px;
    }
    .topSubtitle{
        margin: auto;
        max-width: 42ch;
    }
}
@media screen and (max-width: 768px) {
    .topic{
        text-align: start;
    }
    .topTitle{
        font-size: 40px;
        line-height: 44px;
    }
    .topSubtitle{
        font-size: 18px;
        line-height: 30px;
    }  
}
@media screen and (max-width: 320px) {
    button{
        padding: 20px 0;
        width: 100%;
        margin: 32px auto 54px auto;
    }
    img{
        width: 100%;
    }
}
</style>