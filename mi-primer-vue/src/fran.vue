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

// Primera practica con array constante
const ArrayFruutas = [
  {
    name: "Pera",
    price: "$3.89",
    description: "Una pera perita perota"
  },
  {
    name: "Manzana",
    price: "$1.29",
    description: "Una manzana manzanita manzanota"
  },
  {
    name: "Platano",
    price: "$10.50",
    description: "Un platanote esta bien caro"
  },
  {
    name: "Uva",
    price: "$0.89",
    description: "Una uva, esta bien chikita"
  }
];

// Recoriendo un objeto
const objetoFruta = {
  name: "Manzana",
  price: "$1.29",
  description: "Una manzana manzanita manzanota",
  id: 1
};
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
    <br>
    <ul>
      <li
          v-for="(fruta, index) in ArrayFruutas"
          :key="fruta.name">

        {{ index+1 }} - {{(fruta.name)}}, {{fruta.price}}
      </li>
    </ul>
    <br>
    <ul>
      <li
          v-for="(fruta, propiedad, index) in objetoFruta"
          :key="fruta.id">
        {{index+1}} - {{propiedad}} - {{fruta}}
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