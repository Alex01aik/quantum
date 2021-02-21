<template>
    <div class="comment">
        <div class="commentator">
            <img
                :src="require('../assets/' + comment.portret)"
                alt="portret"
                class="portret"/>
            <div class="commentatorInfo">
                <span class="fullname">
                    {{comment.fullname}}
                </span>
                <span class="position">
                    {{comment.position}}
                </span>
            </div>
        </div>
        <div class="text">
            <span class="quotes">”</span>
            <p class="commentBody">
                {{comment.commentBody}}
            </p>
        </div>
        <span class="date">
            {{comment.date}}
        </span>
    </div>
</template>

<script>
export default {
    props: ['comment']
}
</script>


<style scoped>
.comment{
    min-width: 40vw;
}
.commentator{
    display: flex;
    margin-left: 30px;
}
.portret{
    width: 73px;
    height: 73px;
    border-radius: 50%;
}
.commentatorInfo{
    display: flex;
    flex-direction: column;
    margin-left: 30px;
}
.fullname{
    font-size: 18px;
    margin: 8px 0;
}
.position{
    font-family: 'Montserrat', sans-serif;
    font-size: 16px;
    color: #4F4F4F;
}
.text{
    display: flex;
    flex-direction: row;
}
.commentBody{
    font-size: 24px;
    line-height: 29px;
    font-weight: 700;
    margin-top: 17px;
    margin-bottom: 31px;
}
.date{
    font-size: 15px;
    color: #6248FF;
    font-weight: 700;
    margin-left: 30px;
}
.quotes{
    font-size: 100px;
    font-family: sans-serif;
    text-shadow: #6248FF 1px 1px 0, #6248FF -1px -1px 0, 
    #6248FF -1px 1px 0, #6248FF 1px -1px 0;
    color: white;
}
@media screen and (max-width: 768px) {
    .comment{
        margin-top: 48px;
        text-align: center;
        min-width: 66vw;
    }
    .commentator{
        margin: 0 auto;
        width: fit-content;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    .commentatorInfo{
        margin: 0;
    }
    .text{
        flex-direction: column;
        
    }
    .quotes{
        margin-bottom: -70px;
    }
}
@media screen and (max-width: 480px) {
    .comment{
        margin-top: 0;
        min-width: 280px;  
    }
}
</style>