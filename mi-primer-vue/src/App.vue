<script setup>
 // Creación de constante
 const name = 'Vue Dinamico';

 // Creación de constantes para los estilos
 const stylecolor = "color: blue";

 // Constante de array de colores
 const arraycolor = ["blue", "green", "red"];

 // Array de frutas
 const arrayFrutas = ["🍎","🍏","🍅","🍇","🍈"];

 // Constante Booleana
 const activo = true;
</script>

<template>
  <center>
    <h1>Hola Mundo {{name.toUpperCase()}}</h1>
    <br>
    <h2 v-bind:style="stylecolor">Soy de color azul</h2>
    <br>
    <h2 :style="'color: ${arraycolor[2]}'">Soy batman</h2>
    <br>
    <h2 v-if="activo">Estoy activo</h2>
    <p v-else>Estoy inactivo</p>

    <h2>{{arrayFrutas}}</h2>
    <br>
    <h1 style="text-decoration: underline">Ordenación de Frutas</h1>
    <ul>
      <li
        v-for="(fruta, index) in arrayFrutas">
        {{ index+1 }} - {{(fruta)}}
      </li>
    </ul>
  </center>

</template>

<style>
  h1{
    color: red;
    text-align: center;
  }

</style>