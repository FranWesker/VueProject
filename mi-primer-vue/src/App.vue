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

  const valiNumRepe = computed(() =>{
    const numbusc = arrayFavoritos.value.find((num) => num === contar.value);
    return numbusc || numbusc === 0;
  });
</script>

<template>

    <div class="container text-center mt-3">
      <h1 style="text-decoration: underline">Pruebas 2 {{name.toUpperCase()}}</h1>
      <div class="btn-group">
        <button @click="increment" class="btn btn-success">Incrementar</button>
        <button @click="decrement" class="btn btn-danger">Decrementar</button>
        <button @click="reset" class="btn btn-secondary">Resetear Contador</button>
        <button @click="anadir" :disabled="valiNumRepe" class="btn btn-primary">Añadir</button>
      </div>

      <br>
      <h2 :class="classCounter">Contador: {{contar}}</h2>
      <br>
      <h2>Lista de números</h2>

      <ul class="list-group mt-4">
        <li class="list-group-item"
            v-for="(num, index) in arrayFavoritos" :key="index"
        >
          {{num}}
        </li>
      </ul>
    </div>

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