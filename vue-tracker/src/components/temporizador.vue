<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
            <Cronometro :tempoEmSegundos="tempoEmSegundos"></Cronometro>
            <Botao @clicado="iniciar" 
                icone="fas fa-play" 
                texto="Play" 
                :desabilitado="DisableTempo">
            </Botao>
            <Botao @clicado="finalizando" 
                icone="fas fa-stop" 
                texto="Stop" 
                :desabilitado="!DisableTempo">
            </Botao>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import Botao from './Botao.vue';
import Cronometro from './cronometro.vue';

export default defineComponent({
    name: 'temporizador-vue',
    emits: ['aoTemporizadorFinalizado'],
    components: {
    Cronometro,
    Botao
},
    data() {
        return {
            tempoEmSegundos: 0,
            cronometrado: 0,
            DisableTempo: false
        }  
    },
    
    methods: {
        iniciar() {
            //temporizador com alerta de 15 min
            //iniciar(): void {
            //const minutos = 15 * 60 * 1000;
            //this.intervalo = setInterval(() => {
             //   alert("Hora de fazer um intervalo!");
            //}, minutos);
        //},
            this.DisableTempo = true
            this.cronometrado = setInterval(() => {
                this.tempoEmSegundos++
            },1000)
            console.log('iniciando cronometro');
        },
        finalizando() {
            console.log('terminou!');
            this.DisableTempo = false
            clearInterval(this.cronometrado);
            this.$emit('aoTemporizadorFinalizado', this.tempoEmSegundos);
            this.tempoEmSegundos = 0;
        }
    }
});
</script>