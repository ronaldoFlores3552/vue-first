<script setup>
import {ref} from "vue";
const name="Vue 3"; 
const contador= ref(0);

const handClick=(mensaje)=>{
  console.log(mensaje);
}

const Aumentar=()=>{
  contador.value++;
}
const Disminuir=()=>{
  contador.value--;
}

</script>

<template>
  <h1>
    Mi {{name.toUpperCase()}}
  </h1>
  <!--
    <button v-on:click="handClick">
      Activado
    </button> 
  -->
  <h2 v-bind:class="contador >0 ? 'positive' : 'negative'">{{ contador }}</h2>

  <button @click.right="Aumentar">
    Aumentar
  </button>

  <button @click="Disminuir">
    Disminuir
  </button>


</template>

<style>
.positive{
  color:green;
}
.negative{
  color:red;
}
</style>