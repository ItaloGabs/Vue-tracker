<template>
    <Box>
        <div class="column is-7">
            {{tarefa?.descricao || 'Tarefa sem titulo'}}
        </div>
        <div class="column">
            <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
        </div>
    </Box>
</template>
<script lang="ts">
import { defineComponent, PropType } from 'vue';
import Cronometro from './cronometro.vue';
import ITarefa from '@/interface/ITarefa';
import Box from './Box.vue';

export default defineComponent({
    name: "TarefaForm",
    components: { Cronometro, Box },
    props: {
        tarefa: {
            type: Object as PropType<ITarefa>,
            required: true
        }
    }
});
</script>
