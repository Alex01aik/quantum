<template>
     <div class="stepsBlock container">
            <h2 class="blockTitle">
                Getting Started Is Fast & Easy
            </h2>
            <div class="steps">
                <Step
                    v-for="step of steps"
                        :key="step.number"
                        :step="step"
                        :isLast="last===step"
                    />
            </div>
        </div>
</template>

<script>
import Step from './Step'

export default {
    props: ['steps'],
    computed: {
        last: function () {
            return this.steps[this.steps.length - 1]
        }
    },
    components: {
        Step
    }
}
</script>

<style scoped>
.stepsBlock{
    padding-top: 140px;
}
.blockTitle{
    margin-bottom: 68px;
}
@media screen and (max-width: 768px) {
    .stepsBlock{
        padding-top: 120px;
    }
    .blockTitle{
    margin-bottom: 56px;
    }
}
@media screen and (max-width: 480px) {
    .stepsBlock{
        padding-top: 80px;
    }
    .blockTitle{
    margin-bottom: 40px;
    }
}

</style>