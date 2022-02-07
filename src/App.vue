<template>
 <!--  <img alt="Vue logo" src="./assets/logo.png"> -->
  <HelloWorld msg="Mitos de la NBA" autor="Pablo"/>
<formulario-persona @add-persona="agregarPersona" />

<tabla-personas :personas="personas" />

</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TablaPersonas from './components/TablaPersonas.vue'
import FormularioPersona from './components/FormularioPersona.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TablaPersonas,
    FormularioPersona
  }, 
  data(){
    return{
      personas:[
        {
          id:"100",
          nombre:"Michael Jordan",
          equipo:"Chicago bulls",
          correo:"michael@gmail.com"
          },
          {
          id:"200",
          nombre:"Bryan Scoot",
          equipo:"LA Lakers",
          correo:"bryan@gmail.com"
          },
          {
          id:"300",
          nombre:"Kevin Mchale",
          equipo:"Celtics Boston",
          correo:"kevin@gmail.com"
          }

      ]//cierra array personas

      

      }//cierra return
    },//cierra data
methods: {

    agregarPersona(persona) {

    let id = 0;

if (this.personas.length > 0) {

id = this.personas[this.personas.length - 1].id + 1;

}

this.personas= [...this.personas, { ...persona, id}];

}

}
    
}//cierra default
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
