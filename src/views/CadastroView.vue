<template>
  <div class="main_container">
    <h1>Exibir veículos cadastrados</h1>

    <Dashboard/>
  </div>
</template>

<script>
  import Dashboard from '../components/Dashboard.vue'

  export default {
    name: "CadastroView",
    components: {Dashboard}
  }

</script>
