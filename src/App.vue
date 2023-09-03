<script setup>
const name="Vue 3";
const colorAzul="color: blue";
const arrayColores=["blue", "red","peru"];
const activo= true;
const arrayFrutas = [
    {
        name: "Manzana",
        price: "$1.00",
        description: "Una manzana",
        stock: 0,
    },
    {
        name: "Pera",
        price: "$2.00",
        description: "Una pera",
        stock: 10,
    },
    {
        name: "Naranja",
        price: "$3.00",
        description: "Una naranja",
        stock: 20,
    },
];

</script>

<template>
  <h1>
    Mi {{name.toUpperCase()}}
  </h1>

  <!--<h2 v-bind:style="colorAzul">Soy azul</h2>-->
<h2 :style="`color: ${arrayColores[2]}`">Soy peru</h2>

  <p>{{ arrayColores }}</p>
  <p>{{ activo ? 'Estoy pila': 'No estoy pila' }}</p>
  <!--<p>{{ activo ? 'Estoy pila': 'No estoy pila' }}</p>-->
  <p v-if="activo">Estoy pila</p>
  <p v-else-if="activo===false">Estoy pila</p>
  <p v-else>Estoy pila</p>
  <!-- <p v-if="!activo">Estoy pila</p> -->
  <ul>
    <template v-for="fruta in arrayFrutas" :key="name">
      <li v-if="fruta.stock>0">
        {{fruta.name}} - {{ fruta.price }}
      </li>
    </template>

  </ul>
</template>

<style>

</style>