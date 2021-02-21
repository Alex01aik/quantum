<template>
    <div class="commentsBlock container">
        <div class="commentsTitle">
            <h2 class="blockTitle">
                People love Big Invest
            </h2>
            <div class="carouselButtons">
                <button @click="left">
                    <div class="buttonIcon left"></div>
                </button>
                <button @click="right">
                    <div class="buttonIcon right"></div>
                </button>
            </div>    
        </div>
        <div class="carousel">
            <div class="carouselItems"
                :style="{ 'margin-left': '-' + (100 * currentComment) + '%'}">
                <Comment
                    v-for="comment in comments"
                        :key="comment.date"
                        :comment="comment"/>
                </div>
        </div>
        
    </div>
</template>

<script>
import Comment from './Comment'
export default {
    props: ['comments'],
    components: {
        Comment
    },
    methods: {
        left() {
            if(this.currentComment>0){
                this.currentComment--
            } else {
                this.currentComment = this.comments.length - 1
            }
        },
        right() {
            if(this.currentComment < this.comments.length - 1){
                this.currentComment++
            } else {
                this.currentComment = 0
            }
        }
    },
    mounted() {
        let vm = this
        setInterval(function () {
            vm.right()
        }, 5000)
    },
    data(){
        return {
            currentComment: 0
        }
    }
}
</script>

<style scoped>
.commentsBlock{
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-top: 140px;
}
.carousel{
    max-width: 600px;
    overflow: hidden;
    margin: 0 auto;
}
.carouselItems{
    display: flex;
    flex-direction: row;
    transition: all ease 1s;
}
.carouselButtons{
    margin-top: 39px;
    width: 112px;
    display: flex;
    justify-content: space-between;
}
button{
    width: 48px;
    height: 48px;
    color: black;
    background-color: white;
    border:1px solid #E0E0E0;;
    border-radius: 50%;
}
.buttonIcon{
    border: solid black;
    border-width: 0 3px 3px 0;
    display: inline-block;
    padding: 3px;
}
.left{
    transform: rotate(135deg);
}
.right{
    transform: rotate(-45deg);
}
button:hover{
    border: 1px solid #6248FF;
}
@media screen and (max-width: 768px) {
    .commentsBlock{
        flex-direction: column;
        align-items: baseline;
        margin-top: 120px;
        margin-bottom: 120px;
    }
    .carouselButtons{
        position: absolute;
        margin-top: 207px;
        width: 90%;
    }
    .carousel{
        width: 508px;
    }
}
@media screen and (max-width: 480px) {
    .stepsBlock{
        margin-top: 80px;
        margin-bottom: 80px;
    }
    .blockTitle{
        margin-bottom: 40px;
    }
    .carousel{
        width: 280px;
    }
    .carouselButtons{
        margin-top: 438px;
    }
}
</style>