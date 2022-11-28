<template>
  <div id="app">
    <Navbar :logo="logo_src" :alt="app_name"/>

    <router-view/> 

    <Footer/>

  </div>
 
</template>

<script>
  import Navbar from './components/Navbar.vue';
  import Footer from './components/Footer.vue';
  import HomeView from './views/HomeView.vue';

  export default {
    components: {
    Navbar,
    Footer,
    HomeView
}, 
    data () {
      return {
        logo_src: "/img/carro-esporte.png",
        app_name: "Cadastre o carro no estacionamento",
        banner_src:"/img/carro.jpg",
        bannnerAlt: "Imagem de um estacionamento"
        
      }
    }
  }
</script>

<style>

*{
  margin:0px;
  padding:0px;
  box-sizing: border-box;
  font-family: Arial, Helvetica, sans-serif;
}

.main_container{
  margin:40px;
  min-height: 250px;
}

h1{
  text-align: center;
  font-size: 42px;
  margin-bottom: 40px;
  color: #222;
}

</style>
