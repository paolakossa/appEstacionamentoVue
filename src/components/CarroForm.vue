<template>

<div>
   
    <Mensagem :msg="msg" v-show="msg"/>
    
    <form id="carro-form" @submit="createCarro">

        <div class="input-container">

            <label for="nome">Nome da pessoa: </label>
            <input type="text" id="nome" v-model="nome" placeholder="Informe o seu nome">

        </div> 

        <div class="input-container">

        <label for="nomeCarro">Nome do carro: </label>
        <input type="text" id="nomeCarro" v-model="nomeCarro" placeholder="Informe o seu nome do carro">

        </div> 

        <div class="input-container">

        <label for="placaCarro">Placa do carro: </label>
        <input type="text" id="placaCarro" v-model="placaCarro" placeholder="Informe a placa do carro">

        </div> 

        <div class="input-container">

        <label for="hora">Horário de entrada: </label>
        <input type="text" id="hora" v-model="hora" placeholder="Informe o horário de entrada">

        </div> 

        <div class="input-container">

        <input type="submit" class="submit-btn" value="Cadastrar o carro">

        </div> 

    </form>
</div>

</template>

<script>

    import Mensagem from './Mensagem.vue';

    export default {
        name: 'CarroForm',
        data(){
            return {
                nome: null,
                nomeCarro: null,
                placaCarro:null,
                hora:null,
                msg: null
            }
        },
        methods: {
            async createCarro(e) {
                e.preventDefault();
                const data = {
                    nome: this.nome,
                    nomeCarro: this.nomeCarro,
                    placaCarro: this.placaCarro,
                    hora: this.hora,
                    status:"Solicitado"

                }; 

                const dataJson = JSON.stringify(data); 

                //Fazendo um POST

                const req = await fetch("http://localhost:3000/carros", {
                    method:"POST",
                    headers: {"Content-Type": "application/json"},
                    body: dataJson
                });

                const res = await req.json(); 

                //mensagem de cadastro com sucesso

                this.msg = `${this.nome}, carro cadastrado com sucesso. Obrigado!`;

                //Limpar a mensagem após um tempo

                setTimeout(() => this.msg = "", 3000);

                //Limpar os campos

                this.nome = "";
                this.nomeCarro= "";
                this.placaCarro="";
                this.hora= ""; 
            }
        }, 
        components: {
            Mensagem
        }
    }

</script>

<style scoped>

#carro-form{
    width: 300px;
    margin:0 auto;
}

.input-container{ 
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
}

label{
    font-weight: bold;
    margin-bottom: 15px;
    color: #222;
    padding: 5px 10px;
    border-left: 4px solid #3F7FFB;
}

input {
    padding: 5px 10px;
    width: 300px;
}

.submit-btn{
    background-color: #3F7FFB;
    color: #fff;
    font-weight: bold;
    padding: 10px;
    font-size: 16px;
    border: 2px solid #fff;
    cursor: pointer;
    transition: .5s;
}

.submit-btn:hover{
    background-color: #DC3535;
    font-size: 18px;
}

</style>