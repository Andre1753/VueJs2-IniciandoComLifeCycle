<template>
    <div class="row"> <!--root element -->
        <h1 @click="clique">Campeonato Brasileiro - Série A - 2021</h1><br>
        <h4>Feito por {{nome}}</h4>    
    </div>
</template>

<script>
    export default {
        data(){
            return {
                nome: 'Andre Luiz',
                variavel: null
            }
        },
        beforeCreate(){
            //criar coisa no this
            //verificar se o usuario está autenticado pra definir configuracoes
            //verificar informacoes no localstorage
            console.log(Object.assign({}, this),'beforeCreate');
        },
        created(){
            //this.variavel = new Date();
            console.log(Object.assign({}, this),'create');
        },
        beforeMount(){
            //this.$attrs['']
            // aqui já tem attrs
            console.log(Object.assign({}, this),'beforeMount');
        },
        mounted(){
            console.log(Object.assign({}, this),'mounted');
        },
        beforeUpdate(){
            console.log(Object.assign({}, this),'beforeUpdate');
        },
        updated(){
            console.log(Object.assign({}, this),'updated');
        },
        beforeDestroy(){
            console.log(Object.assign({}, this),'beforeDestroy');
        },
        destroyed(){
            console.log(Object.assign({}, this),'destroyed');
        },
        methods: {
            clique() {
                this.nome = 'GiantDwarf';
                console.log('rolou um update');
            }
        }
    }
</script>