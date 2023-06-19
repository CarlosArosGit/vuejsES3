<template>
  <div id="app">
    <ComponenteEva3 v-bind:juegos="arregloJuegos" v-on:juegoAEliminar="eliminarDelArregloJuegos"
      v-on:juegoAInsertar="insertarJuegoEnElArreglo" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ComponenteEva3 from './components/ComponenteEva3.vue'
export default {
  name: 'App',
  components: {
    ComponenteEva3
  },
  data: function () {
    return {
      arregloJuegos: ['Arena of Valor', 'Pokemon Unite', 'Donkey Kong', 'Heroes of the Storm', 'Valorant'],
    }
  },
  methods: {
    eliminarDelArregloJuegos: function (indiceJuego) {
      this.arregloJuegos.splice(indiceJuego, 1);
    },
    insertarJuegoEnElArreglo: function (nombreJuego) {
      this.arregloJuegos.push(nombreJuego);
    },
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
