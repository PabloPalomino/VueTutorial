<template>

<div id="formulario-persona">

<form @submit.prevent="enviarFormulario">

<div class="container">

<div class="row">



<div class="col-md-4">


<div class="form-group">

<label>Jugador</label>

<input v-model="persona.nombre" type="text" class="form-control" />

</div>

</div>

<div class="col-md-4">

<div class="form-group">

<label>Equipo</label>

<input v-model="persona.equipo" type="text" class="form-control" />

</div>

</div>

<div class="col-md-4">

<div class="form-group">

<label>Email</label>

<input v-model="persona.correo" type="email" class="form-control" />

</div>

</div>

</div>

<div class="row">

<div class="col-md-4">

<div class="form-group">

<button class="btn btn-primary">Añadir persona</button
>

</div>

</div>

</div>

</div>

</form>

</div>

</template>


<script>
export default {

name: 'formulario-persona',

data() {

return {

    persona: {
        id: '',
        jugador: '',
        equipo: '',
        correo:'',
},
}

},

    methods: {

    enviarFormulario() {

        this.$emit('add-persona', this.persona);

    }

},


}
</script>
