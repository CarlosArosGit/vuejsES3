<template>
    <div class="componente3">
        <h2>Componente Sesión 3</h2>
        <div id="contenedorPadre">
            <div id="contenedorIzquierda">
                <table border="1">
                    <tr>
                        <th>#</th><th>Juego</th><th>Eliminar Juego</th>
                    </tr>
                    <tr v-for="(juego, index) in juegos" :key ="index" >
                        <td>{{ index }}</td><td>{{ juego }}</td><td><button v-on:click="eliminarJuego(index)">Eliminar</button></td>
                    </tr>
                </table>
            </div>
            <div id="contenedorDerecha">
                <form>
                    <label for="txtNombreJuego">Nombre Juego:</label>
                    <input type="text" id="txtNombreJuego" v-model="nombreJuegoAInsertar"><br>
                    <button v-on:click.prevent="insertarJuego">Insertar el Juego</button>

                </form>
            </div>
        </div>
    </div>
  </template>
  
  <script>
export default{
    name:'Componente3',
    props:{
        juegos:{
            type: Array,
            required: true,
        }
    },
    data: function(){
        return{
            nombreJuegoAInsertar:'',
        }
    },
    methods:{
        eliminarJuego: function(indice){
            this.$emit('juegoAEliminar', indice);
        },
        insertarJuego: function(){
            this.$emit('juegoAInsertar', this.nombreJuegoAInsertar);
            this.nombreJuegoAInsertar = '';
        },
    },

}
</script>


<style scoped>
#contenedorIzquierda{
    width: 59%;
    display: inline-block;
}

#contenedorDerecha{
    width: 39%;
    display: inline-block;
}
</style>