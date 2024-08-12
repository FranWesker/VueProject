<script setup>
const name = "Vue Pagina";
// metodo methods
const handleClick= (message) => {
  console.log(message)
}
</script>

<template>
  <center>
    <h1>Pruebas 2 {{name.toUpperCase()}}</h1>
    <button v-on:click.right="handleClick('Texto Right')">Activame Right</button>
    <button @click.left="handleClick('Texto Left')">Activame Left</button>
    <button @click.middle="handleClick('Texto Middle')">Activame Middle</button>
  </center>

</template>

<style>
h1{
  color: red;
  text-align: center;
}

</style>