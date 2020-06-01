<template>
    <div id="app">
        <div class="container mt-5">
          <h1>{{titulo}}</h1>
          <br>
            <input class="form-control form-control-lg" placeholder="Ingrese una tarea" type="text" v-model="nuevatarea" >
            
            <button type="button" class="boton_1" @click="Agregar">Añadir</button>
        </div>

        <ul>
            <HelloWorld v-for="(tarea, index) in tareas"
                v-bind:tarea="tarea"
                v-bind:index="index"
                v-bind:key="index"
                v-on:borrarhijo="borrarnombre">
             </HelloWorld>
        </ul>
    </div>
</template>

<script>
import  HelloWorld from './components/HelloWorld.vue' 
export default {
  name:'App',
  components: {HelloWorld},
    data(){
      return{
      tareas : [],
      nuevatarea: "",
      titulo:"Lista de tareas "
    }
     },
methods:{
  Agregar(){
    this.tareas.push({
      tarea: this.nuevatarea
    });
    this.nuevatarea=""; 
  },

  borrarnombre(index){
    this.tareas.splice(index, 1);
    console.log(index);
    
  },
  Agregar() {
      if (this.nuevatarea ===""|| this.nuevatarea.length <4 ) {
        alert('El largo de la palabra a agregar como tarea debe ser mayor a 4 carácteres')
      } else {
         this.tareas.push({
        tarea: this.nuevatarea,
      });
      this.nuevatarea = "";
    }
      },
},
}



</script>

<style>
#app{ 
max-width: 50%;
max-height: 50%;
background-color: rgb(192, 255, 231);
border-radius: 10%;
}
input{
  padding-top: 3em;
}
h1{
  font-family: "Comic Sans MS", cursive, sans-serif;
  font-size: 50px;
}

  .boton_1{
    
    text-decoration: none;
    padding: 3px;
    padding-left: 10px;
    padding-right: 10px;
    font-family: helvetica;
    font-weight: 300;
    font-size: 25px;
    font-style: italic;
    color: #005665;
    background-color: #e6e7da;
    border-radius: 15px;
    border: 3px double #006505;
  }
  .boton_1:hover{
    opacity: 0.6;
    text-decoration: none;
  }

</style>