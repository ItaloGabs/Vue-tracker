<template>
    <div class="is-flex is-align-items-center is-justify-content-space-between">
                <Cronometro :tempoEmSegundos="tempoEmSegundos"></Cronometro>
                <button class="button" @click="iniciar" :disabled="DisableTempo">
                    <span class="icon">
                        <i class="fas fa-play"></i>
                    </span>
                    <span>play</span>
                </button>
                <button class="button" @click="finalizando" :disabled="!DisableTempo">
                    <span class="icon">
                        <i class="fas fa-stop"></i>
                    </span>
                    <span>stop</span>
                </button>
    </div>
</template>
<script lang="ts">
import { defineComponent } from 'vue';
import Cronometro from './cronometro.vue';

export default defineComponent({
    name: 'temporizador-vue',
    components: {
        Cronometro
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
        }
    }
});
</script>