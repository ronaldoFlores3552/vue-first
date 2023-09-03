<script setup>
const name="Vue 3"; 
const handClick=(mensaje)=>{
  console.log(mensaje);
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
  <button @click.right="handClick('right')">
    Texto Right
  </button>
  <button @click="handClick('middle')">
    Texto middle
  </button>
  <button @click="handClick('left')">
    Texto Left
  </button>
  
</template>

<style>

</style>