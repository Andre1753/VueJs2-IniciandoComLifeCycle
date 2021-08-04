<template>
    <div class="container">
        <button @click="mostrarTitulo = false" >Destruir Título</button>
        <titulo v-if="mostrarTitulo" id="teste" teste-mounted="ficou disponivel"></titulo>
        <div class="row">
            <div class="col-md-12">
                <!--<novo-jogo :times="times" @novo-jogo="showPlacar($event)"></novo-jogo>-->
                <novo-jogo :times="times"></novo-jogo>
            </div>
        </div>
        <br>
        <div class="row">
            <!--<div class="col-md-12" v-show="visao!='tabela'">-->
            <!--<placar :time-casa="timeCasa" :time-fora="timeFora" @fim-jogo="showTabela($event)"></placar>-->
            <!--</div>-->
            <div class="col-md-12" v-show="visao === 'tabela'">
                <tabela-clubes :times="times"></tabela-clubes>
            </div>
        </div>
    </div>
</template>´

<script>
    export default {
        data() {
            return {
                mostrarTitulo: true,
                times: [],
                timeCasa: null,
                timeFora: null,
                visao: 'tabela'
            };
        },
        methods: {
            showTabela(event) {
                console.log(event);
                this.visao = 'tabela'
            },
            showPlacar({timeCasa, timeFora}) {
                this.timeCasa = timeCasa;
                this.timeFora = timeFora;
                this.visao = 'placar';
            }
        }
    }
</script>