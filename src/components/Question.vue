<template>
    <details class="question">
        <summary class="questionTitle">
            <span>{{question.title}}</span>
        </summary>
            <p class="questionDescription">
                {{question.description}}
            </p>
    </details>
</template>

<script>
export default {
    props: ['question'],
    methods: {
        opencloseHandler(event) {
            console.log(event)
        }
    }
}
</script>

<style scoped>
details summary::-webkit-details-marker {
    display:none;
}
details:not([open]) > summary::after{
    content: '+';
    font-size: 26px;
}
details[open] > summary::after{
    content: '✕';
    font-size: 20px;
    font-weight: 700;
}
.question{
    margin: 8px auto;
    border: 2px solid #6248FF;
    border-radius: 20px;
    max-width: 995px;
    padding: 32px 40px;
}
.questionTitle{
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-size: 24px;
    line-height: 29px;
}
.questionDescription{
    margin-top: 24px;
    margin-bottom: 0;
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    line-height: 27px;
    color: #4F4F4F;
    max-width: 70ch;
}
@media screen and (max-width: 320px) {
    .question{
        padding: 24px 16px;
    }
    .questionTitle{
        font-size: 18px;
        line-height: 22px;
    }
    .questionDescription{
        font-size: 16px;
        line-height: 27px;
    }
}
</style>