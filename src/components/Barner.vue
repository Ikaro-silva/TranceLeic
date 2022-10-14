<template>
    <div id="barner">
        <div id="img">
            
        </div>
        <div id="formulario" @submit="createCliente">
            <Msg  :Msg="Msg" v-show="Msg" />
            <form>
                <div id="container-form" class="form-container">
                    <label for="nome">Clinete:</label>
                    <input type="text" id="nome" v-model="nome" placeholder="Nome do cliente" required> 
                </div>
              
                <div id="container-form" class="form-container" >
                    <label for="marcacao">Data /horario</label>
                    <input type="datetime" id="marcacao" v-model="marcacao" placeholder="ex:20/02/2003-15:00" required>
                </div>
                <div id="container-form" class="form-container">
                    <label for="estilo">Estilo de trança</label>
                    <select name="" id="estilo" v-model="estilo" placeholder="Estilos" required>
                        
                        <option value="">escolha o estilos</option>
                        <option value="Box braids">Box braids</option>
                        <option value="Nagô">Nagô</option>
                        <option value="Twist">Twist</option>
                        <option value="Boxeadora">Boxeadora</option>
                    </select>
                </div>
                <div  class="checkBox">
                    <input type="radio" name="fibra" v-model="fibra" value="Fibra empresa">
                    <span>Fibra empresa</span>
                
                    <input type="radio" name="fibra"  v-model="fibra" value="Fibra clente">
                    <span>Fibra clente</span>
                </div>
                <div><input type="submit" class="btn" value="Agendar"></div>
            </form>
        </div>
    </div>
</template>

<script>
    import Msg from './Msg.vue'
    export default{
        name:"Barner",
        components:{Msg},
        data(){
            return{
                nome:null,
                marcacao:null,
                estilo:null,
                fibra:null,

                Msg:null
            }
            
        },
        methods:{
            async createCliente(e){
                e.preventDefault()
                const data ={
                    nome:this.nome,
                    marcacao:this.marcacao,
                    estilo:this.estilo,
                    fibra:this.fibra
                }
                const dataJson = JSON.stringify(data) //enviando do formulario para o falso banco de dados 

                const req =await fetch("http://localhost:3000/trancas",{
                    method:"POST",
                    headers:{"Content-Type":"application/json"},
                    body:dataJson
                })
              
                const res = await req.json()

                // COLOCAR MENSAGEM NOSISTEMA
                this.Msg=`Agendado com sucesso`
                //Pagando mensagem 
                setTimeout(()=>this.Msg="",3000)
                //apagar conteudo do forme
                this.nome="",
                this.marcacao="",
                this.estilo="",
                this.fibra=""
                
                
            }
        }

    }

</script>

<style scoped>
    #barner{
        display: flex;
    }
    #img {
        background-image: url('../../public/img/baner.jpg');
        background-repeat: no-repeat;
        background-size:contain;
        width:40vw;
        height:500px;
        margin-left:40px;
    }
    #formulario{
        margin-top: 50px;
        margin:auto;
    }
    #container-form{
        display: flex;
        flex-direction:column;
        margin-bottom: 20px;
        
    }
    .form-container{
        padding: 5px 10px;
        width: 400px;
        color: white;
    }
    .form-container input{
        color: white;
        height:25px;
        background-color: rgba(0, 0, 0, 0.651);
    }
    .form-container select{
        background-color: rgba(0, 0, 0, 0.651);
        color: white;
        height:25px;
    }
    .checkBox{
        text-align: center;
        color: white;
    }
    .checkBox input{
        margin-left:30px;
        
    }
    .checkBox span{
        margin-left: 6px;
    }
    .btn{
        display: block;
        margin: auto;
        margin-top:40px;
        width:350px;
        background-color: #e69010;
        font-weight: bold;
        padding:10px 0;
        font-size: 1em;
        border: 3px solid #523101;
        cursor:pointer;
    }
    .btn:hover{
        color: #ff9c07;
        background-color: transparent;
        transition: 0.3s;
    }
   
</style>