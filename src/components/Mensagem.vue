<template>

    <div class="mensagem-container">
        <h2>{{msg}}</h2>
    </div>

</template>

<script>
    export default {
        name: "Mensagem",
        props: {
            msg: String
        }
    }
</script>

<style scoped> 

.mensagem-container{
    color: #fff;
    background-color:#68B984;
    border: 2px solid #fff;
    border-radius: 5px;
    padding: 10px;
    max-width: 400px;
    margin: 30px auto;
}

</style>