<template>
  <theHeader/>
  <router-View />
  <theFooter/>
</template>

<script>
  import theHeader from './components/theHeader.vue'
  import theFooter from './components/theFooter.vue'
  export default{
    name:'App',
    components:{
      theHeader,
      theFooter
    }
  }

</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    
  }
  body{
    background-color: #000000e8;
  }

</style>
