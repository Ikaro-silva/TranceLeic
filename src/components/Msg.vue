<template>
    <div class="msg-container">
        {{Msg}}
    </div>
</template>

<script>
    export default{
        name:'Msg',
        props:{
            Msg:String
        }
    }
</script>

<style>
    .msg-container{
        background-color:rgba(211, 211, 211, 0.534);
        color: black;
        font-weight: bold;
        padding: 5px;
        margin: auto;
        margin-bottom: 20px;
        width:380px;
    }
    @media only screen and (max-width:442px){
        .msg-container{
            width:150px;
        }
    }

</style>