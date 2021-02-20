<template>
    <button>
            {{text}}
    </button>
</template>

<script>
export default {
    props: ['text']
}
</script>

<style scoped>
button{
    background-color: #6248FF;
    color: white;
    border: none;
    border-radius: 60px;
    font-family: 'Museo Sans Cyrl', sans-serif;
    text-transform: uppercase;
    font-size: 16px;
    padding: 20px 64px;
    margin: 32px;
    width: fit-content;
    letter-spacing: 0.03em;
    min-width: 168px;
}
button:hover{
    background: #7181FC; 
}
button:disabled{
    background: #7181FC;
    color: #828282;
}
</style>