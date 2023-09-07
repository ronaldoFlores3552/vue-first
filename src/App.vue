<script setup>
import { ref, computed } from "vue";
const name = "Vue 3";
const contador = ref(0);

const arrayNumeros = ref([]);

const handClick = (mensaje) => {
  console.log(mensaje);
}

const Aumentar = () => {
  contador.value++;
}
const Disminuir = () => {
  contador.value--;
}

const computabilidad = computed(() => {
  if (contador.value === 0) {
    return 'zero'
  }
  else if (contador.value > 0) {
    return 'positive'
  } else {
    return 'negative';
  }
});

const add = () => {
  arrayNumeros.value.push(contador.value);
}

const blockBtn = computed(() => {
  const numero = arrayNumeros.value.find((num) => num === contador.value);
  return numero || numero === 0;
});

</script>

<template>
  <div class="container text-center mt-5">

    <h1>
      Mi {{ name.toUpperCase() }}
    </h1>
    <!--
    <button v-on:click="handClick">
      Activado
    </button> 
  -->
    <h2 v-bind:class="computabilidad">{{ contador }}</h2>

    <div class="btn-group">
      <button @click="Aumentar" class="btn btn-success">
        Aumentar
      </button>

      <button @click="Disminuir" class="btn btn-danger">
        Disminuir
      </button>

      <button @click="add" v-bind:disabled="blockBtn" class="btn btn-primary">
        Agregar
      </button>
    </div>
    <div>
      <h2 class="mt-3">Mis Favoritos</h2>
      <ul class="list-group mt-2">
        <li class="list-group-item" v-for="numero in arrayNumeros" key="numero">
          {{ numero }}
        </li>
      </ul>

    </div>

  </div>
</template>

<style>
.positive {
  color: green;
}

.negative {
  color: red;
}

.zero {
  color: peru;
}
</style>