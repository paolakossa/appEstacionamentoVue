<template>
  <div class="main_container home">
    <img src="../../public/img/carro.jpg" id="banner">
    <h1>Cadastrar Veículos</h1>

    <CarroForm/>
    
  </div>
</template>

<script>
  import CarroForm from '../components/CarroForm.vue';

  export default {
    name: "HomeView",
    components: {
      CarroForm
    }
  }
</script>

<style scoped>

#banner{
  width: 100%;
  height: 700px;
}
  
</style>
