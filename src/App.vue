<script setup>
import FormularioComp from './components/FormularioComp.vue';
import useClima from './composables/useClima';
import ClimaComp from './components/ClimaComp.vue';
import SpinnerComp from './components/SpinnerComp.vue';

const { obtenerClima, clima, mostrarClima, cargando } = useClima();
</script>

<template>
  <h1 class="titulo">Buscador de CLima</h1>

  <div class="contenedor buscador-clima">
    <FormularioComp @obtener-clima="obtenerClima"/>

    <SpinnerComp v-if="cargando"/>

    <ClimaComp v-if="mostrarClima" :clima="clima"/>
  </div>

</template>

<style scoped></style>
