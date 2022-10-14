<template>
    <div id="header-main">
        <div id=links>
            <router-link to="/">Home</router-link>
            <router-link to="/Trancas">Tranças</router-link>
            <router-link to="/Clientes">Clientes</router-link>
        </div>

        <router-Link to="/" id="logo">
            <h1>TranceLeic</h1>
        </router-Link>
    </div>
</template>
<script>
    export default{
        name:"theHeader"
    }
</script>

<style scoped>
    #header-main{
        display: flex;
        background-color: black;
        color: white;
        padding: 20px 40px;
        justify-content:space-between;
        
    }
    #links{
        margin: auto 0;
    }

    #header-main  a{
        color:  #e69010;
        text-decoration: none;
        margin-right: 20px;
        font-weight: bold;

    }
    #header-main a:hover{
        color:#b66e02;
        transition: 0.3s;
    }
    #header-main h1{
        color: #ff9c07;
    }


</style>