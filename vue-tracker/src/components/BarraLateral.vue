<template>
<!-- /*Toda parte HTML*/ -->
    <header>
        <img src="../assets/logo.png" alt="">
    </header>
</template>

<script lang="ts">
/*Todo Typescript*/
import { defineComponent } from "vue";

export default defineComponent({
  name: 'BarraLateral'
});
</script>

<style>
/*Toda parte css*/
header {
  padding: 1rem;
  background: #0d3b66;
  width: 100%;
  height: 100vh;
}
@media only screen and (max-width: 768px) {
  header {
    padding: 2.5rem;
    height: auto;
  }
}
</style>
