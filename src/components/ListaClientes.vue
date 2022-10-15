<template>
     <div>
        <h1>Lista de clientes</h1>
        <Msg :Msg="Msg" v-show="Msg" />
         <div id="cliente-table">
            <div>
                <div id="cliente-table-heading">
                    <div class="order-id">#</div>
                    <div>Cliente</div>
                    <div id="data">Data</div>
                    <div>Modelo</div>
                    <div>Fibra</div>
                    <div>Ação</div>
                </div>
                <div id="cliente-table-rows">
                    <div class="cliente-table-row" v-for="tranca in trancas" :key="tranca.id">
                        <div class="order-number">{{tranca.id}}</div>
                        <div>{{tranca.nome}}</div>
                        <div id="marcacao">{{tranca.marcacao}}</div>
                        <div>{{tranca.estilo}}</div>
                        <div>{{tranca.fibra}}</div>
                        <div ><button @click="getdselete(tranca.id)" id="btn">Cancelar</button></div>
         
         
                    </div>
         
                </div>
            </div>
             </div>
     </div>
</template>

<script>
    import Msg from './Msg.vue'
    export default{
        name:'ListaClientes',
        components:{Msg},
        data(){
            return{
                trancas:null,

                Msg:null

            }
        },
        methods:{
            async getClientes(){
                const req = await fetch('http://localhost:3000/trancas')
                const data = await req.json()
                this.trancas = data
                console.log(this.trancas)
            },
            async getdselete(id){
                const req =await fetch(`http://localhost:3000/trancas/${id}`,{
                    method:"DELETE"
                })
                const res=await req.json()

                // COLOCAR MENSAGEM NOSISTEMA
                this.Msg=` ${id}° Cliente  CANCELADO`
                //Pagando mensagem 
                setTimeout(()=>this.Msg="",3000)

                this.getClientes()
            }
        },
        mounted(){
            this.getClientes()
        }
    }
</script>

<style scoped>
     h1{
        background-color: black;
        text-align: center;
        color:white;
        padding-bottom: 20px;
    }
   
    #cliente-table{
        max-width: 1200px;
        margin:0 auto ;
        text-align: center;
    }
    #cliente-table-heading,#cliente-table-rows, .cliente-table-row {
    display: flex;
    flex-wrap: wrap;
    }
    #cliente-table-rows{
        background-color: lightgray;
    }

    #cliente-table-heading{
        background-color:rgb(65, 65, 65);
        font-weight: bold;
        padding: 12px;
        border-bottom: 3px solid #3b3b3b;
        color: #ff9c07;
    }
    #cliente-table-heading div,
    .cliente-table-row div{
        width: 19%;
    }
    .cliente-table-row{
    width: 100%;
    padding: 12px;
    border-bottom: 2px solid #8a8a8a;
    }
    #cliente-table-heading .order-id,
    .cliente-table-row .order-number{
        width: 5%;
    }

    #btn{
        display: block;
        margin: 0 auto;
        background-color: #e69010;
        font-weight: bold;
        padding:2px ;
        border: 3px solid #523101;
        cursor:pointer;
    }
    #btn:hover{
        color: #ff9c07;
        background-color: transparent;
        transition: 0.3s;
    }
    @media only screen and (max-width:442px){
        #btn{
            font-size:0.8em;
        }
        #cliente-table-heading,#cliente-table-rows{
            font-size:0.8em
        }
        .cliente-table-row .order-number{
         width: 2%;
        }
      
    }
        
</style>