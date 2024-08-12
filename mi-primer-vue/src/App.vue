<script setup>
  import {ref} from 'vue'

  const name = "Vue Pagina";
  // metodo methods
  const increment = () =>{
    console.log('aumentar contador')
    contar.value++;
    console.log(contar);
  }
  // variable de contar
  const contar = ref(0);
</script>

<template>
  <center>
    <h1 style="text-decoration: underline">Pruebas 2 {{name.toUpperCase()}}</h1>
    <br>
    <button @click="increment">Incrementar</button>
    <h2>Contador: {{contar}}</h2>
  </center>

</template>

<style>
  h1{
    color: red;
    text-align: center;
  }

</style>