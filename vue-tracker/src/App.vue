<template>
  <main class="columns is-gapless is-multiline">
    <div class="colums is-one-quarter">
      <BarraLateral/>
      
    </div>
    <div class="colums is-three-quarter">
      <Formulario/>

    </div>

  </main>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import BarraLateral from './components/BarraLateral.vue';
import Formulario from './components/formulario.vue';



export default defineComponent({
    name: "App",
    components: { BarraLateral, Formulario }
});
</script>

<style>

</style>
