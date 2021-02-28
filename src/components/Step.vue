<template>
    <div class="step">
        <div class="stepBody">
            <span class="stepNumber">
                {{step.number}}
                </span>
            <h3 class="stepTitle">
                {{step.title}}
                </h3>
            <p class="stepDescription">
                {{step.description}}
            </p>
        </div>   
        <div v-show="!isLast" class="stepPath"></div>
    </div>
</template>

<script>
export default {
    props: ['step', 'isLast']
}
</script>

<style scoped>
.step{
    display: flex;
    width: 100%;
    --violet: #6248FF;
    position: relative;
    margin-top: -30px;
}

.step:first-child{
    margin-top: 0;
}

.step:nth-child(even) {
    margin-left: auto;
    flex-direction: row-reverse;
}

.stepBody{
    padding: 32px;
    width: 38%;
    border: 2px solid var(--violet);
    border-radius: 30px;
}
.stepNumber{
    color: var(--violet);
    font-size: 15px;
    line-height: 18px;
    margin-bottom: 8px;
}
.stepTitle{
    font-size: 24px;
    line-height: 29px;
}
.stepDescription{
    font-family: 'Montserrat', sans-serif;
    font-size: 18px;
    line-height: 30px;
    color: #4F4F4F;
    max-width: 36ch;
}
.stepPath{
    border-top: 3px dashed #6248FF;
    width: 43%;
    height: calc(50% - 30px);
    position: absolute;
    top: 50%;
    left: 38%;
}
.step:nth-child(odd) .stepPath{
    border-right: 3px dashed #6248FF;
    border-radius: 0 60px;
}
.step:nth-child(even) .stepPath{
    left: 19%;
    border-left: 3px dashed #6248FF;
    border-radius: 60px 0;
}
@media screen and (max-width: 768px) {
    .step{  
    margin-top: -60px;
    }
    .stepBody{
    width: 48%;
    }
    .stepPath{
    width: 33%;
    height: calc(50% - 60px);
    left: 48%;
}   
    .step:nth-child(odd) .stepPath{
        border-radius: 0 30px;
    }
    .step:nth-child(even) .stepPath{
        border-radius: 30px 0;
    }
}
@media screen and (max-width: 480px) {
    .step{
        margin: 0;
    }
    .stepBody{
        padding: 24px;
        margin: 12px 0;
        width:100%;
    }
    .stepPath{
        display: none;
    }
}
</style>