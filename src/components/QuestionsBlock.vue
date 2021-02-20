<template>
    <div class="questionsBlock container">
        <h2 class="blockTitle">
            Frequently asked questions
        </h2>
        <Question 
            v-for="question of questions"
                :key="question.title"
                :question="question"/>        
    </div>
</template>

<script>
import Question from './Question'
export default {
    props: ['questions'],
    components: {
        Question
    }
}
</script>

<style scoped>
.questionsBlock{
    margin-top: 140px;
    margin-bottom: 140px;
}
.blockTitle{
    margin-bottom: 68px;
}
@media screen and (max-width: 768px) {
    .stepsBlock{
        margin-top: 120px;
        margin-bottom: 120px;
    }
    .blockTitle{
        margin-bottom: 56px;
    }
}
@media screen and (max-width: 320px) {
    .stepsBlock{
        margin-top: 80px;
        margin-bottom: 80px;
    }
    .blockTitle{
        margin-bottom: 40px;
    }
}
</style>