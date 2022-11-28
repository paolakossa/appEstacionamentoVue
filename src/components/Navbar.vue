<template>
<div id="nav">
    <router-link to="/" id="logo-url">
        <img :src="logo" :alt="alt" id="logo">
    </router-link>

    <nav>
      <router-link to="/">Home</router-link>
      <router-link to="/cadastro">Cadastro</router-link>
    </nav>
</div>
</template>

<script>
    export default {
        name:'Navbar',
        props: ["logo", "alt"] //Logo do projeto e as imagens
    }
</script>

<style scoped>
 #nav {
    background-color: #3F7FBF;
    padding: 15px 50px; 
    display: flex;
    justify-content: flex-end;
    align-items: center;
 }

 #nav #logo-url{
    margin: auto;
    margin-left: 0;
 }

 #logo{
    width: 50px;
    height: 50px;
 }

 nav a{
    color: #fff;
    text-decoration: none;
    margin: 12px;
    transition: 0.5s;
    font-size: 20px;
    
     }
nav a:hover{
    color: #DC3535;
    border-bottom: 2px solid #DC3535;
}
</style>