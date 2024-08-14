<script setup>
  import {ref, computed} from 'vue'

  const name = "Vue Pagina";
  // metodo methods
  const increment = () =>{
    console.log('aumentar contador ++')
    contar.value++;
    console.log(contar.value);
  }
  // funcion decrementar
  const decrement = () =>{
    contar.value--;
    console.log(contar.value);
  }
  // Boton de resetear contador
  const reset = () =>{
    contar.value = 0;
  }
  // variable de contar
  const contar = ref(0);

  const classCounter = computed(() =>{
    if(contar.value === 0){
      return 'zero'
    }
    if(contar.value > 0){
      return 'positive';
    }else {
      return 'negative'
    }
  })

  const arrayFavoritos = ref([])

  const anadir = () =>{
    arrayFavoritos.value.push(contar.value);
  }
</script>

<template>
  <center>
    <h1 style="text-decoration: underline">Pruebas 2 {{name.toUpperCase()}}</h1>
    <br>
    <button @click="increment">Incrementar</button>
    <button @click="decrement">Decrementar</button>
    <button @click="reset">Resetear Contador</button>
    <button @click="anadir">Añadir</button>
    <br>
    <h2 :class="classCounter">Contador: {{contar}}</h2>
    <br>
    <h2>Lista de números</h2>
    {{arrayFavoritos}}
    <ul>
      <li
          v-for="(num, index) in arrayFavoritos" :key="index"
        >
        {{num}}
      </li>
    </ul>
  </center>

</template>

<style>
  h1{
    color: red;
    text-align: center;
  }
  .positive{
    color: green;
  }
  .negative{
    color: red;
  }
  .zero{
    color: peru;
  }
</style>