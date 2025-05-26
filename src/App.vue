<template>
  <div id="app">
    <h1>Proyecto Parcial</h1>
    <ModificadorDeTexto />
  </div>
  <hr>
  <p>Respuesta 1: la forma reducida de v-on:click es @click / Respuesta 2: el modificador trim recorta... Los espacios adelante y atras en una entrada de texto / Respuesta 3: La propiedad routes en la definición del router de Vue.js tiene como función... definir el path y el componente activo para esa ruta</p>
</template>

<script>
import ModificadorDeTexto from './components/ModificadorDeTexto.vue';

export default {
  name: 'App',
  components: {
    ModificadorDeTexto
  }
}
</script>

<style>

</style>
