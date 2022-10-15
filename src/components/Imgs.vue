<template>
    <h1>Trabalhos Feitos...</h1>
    <div id="container-img">
        
        <div classe="banner-img">
        
            <img src="../../public/img/Box-braid-homens.jpg" alt="" class="img-box-braidH">
        
        
            <img src="../../public/img/box-brainds.jpg" alt="" class="img-box-brainds">
        
        
            <img src="../../public/img/nagô.jpg" alt="" class="img-nagô">
        
        
            <img src="../../public/img/trancando.jpg" alt="" class="img-trancando">
        
        
            <img src="../../public/img/trança-nagô.jpg" alt="" class="img-tranca-nago">
        
        
            <img src="../../public/img/tranças-masculino.jpg" alt="" class="img-tranca-Masc">
        
        
            <img src="../../public/img/tranca-afro-twist.jpg" alt="" class="img-twist">
        
        </div>
    </div>
</template>
<script>
    
    export default{
        name:'Imgs'
    }

</script>

<style scoped>
  
    h1{
        background-color: black;
        text-align: center;
        color:white;
    }
    #container-img{
        display: flex;
        justify-content:center;
        align-items: center;
        text-align: center;
        background-image: url('../../public/img/backgroud.jpg');
    }
   
    .img-box-braidH{
        width:350px;
        height:400px;
        padding:20px 10px;
        
    }
    .img-box-brainds{
        height:400px;
        width:350px;
        padding:20px 10px;
    }
    .img-nagô{
        height:400px;
        width: 350px;
        padding:20px 10px;
    }
    .img-trancando{
        width: 90vw;
        height:500px;
        padding:10px;
    }   
    .img-tranca-nago{
        width: 350px;
        height:400px;
        padding:20px 10px;
    }
    .img-tranca-Masc{
        width:350px;
        height:400px;
        padding:20px 10px;
    }
    .img-twist{
        width:350px;
        height: 400px;
        padding:20px 10px;
    }
    @media only screen and (max-width:442px){
        h1{
        background-color: black;
        text-align: center;
        color:white;
        font-size:1.5em;
    }

   
    .img-box-braidH{
        width:320px;
        height:380px;
        padding:20px 10px;
        
    }
    .img-box-brainds{
        height:380px;
        width:320px;
        padding:20px 10px;
    }
    .img-nagô{
        height:380px;
        width: 320px;
        padding:20px 10px;
    }
    .img-trancando{
        width: 90vw;
        height:500px;
        padding:10px;
    }   
    .img-tranca-nago{
        width: 320px;
        height:380px;
        padding:20px 10px;
    }
    .img-tranca-Masc{
        width:320px;
        height:380px;
        padding:20px 10px;
    }
    .img-twist{
        width:320px;
        height: 380px;
        padding:20px 10px;
    }
        
    }
</style>