<template>
      <li>{{tarea.tarea}} <button type="button" class="btn btn-danger" @click="borrar">Eliminar</button> </li>
</template>
<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
listado:""  

  }
},
  props: {
    tarea: Object,
    index: Number,
       
  },
  methods: {
    borrar() {
       this.$emit('borrarhijo', this.index)
  },
}
}
</script>

<style>

li{
background-color: rgb(192, 255, 231);
text-align: center;
font-family: "Comic Sans MS", cursive, sans-serif;
 font-size: 2em;
}
</style>