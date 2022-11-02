
<script setup>
import { ref } from 'vue';

const header = ref('Shopping List App')
const items = ref([
  {id: 0 , label: "Comida boa doce ", price: 5},
  {id: 1, label: "Comida boa salgada ", price: 10},
  {id:2 , label: "Sem comida",}
])

function mudarValorLabel(id){
 
  items.value[id].label =  `O preço é ${items.value[id].price ?? "Sem preço"}`;
  console.log("🚀 ~ file: App.vue ~ line 14 ~ mudarValorLabel ~ items.value", items.value)
}

</script>


<template>
 <h1>{{header}}</h1>
<ul>
  <li v-for="item in items" :key='item.id' @click='mudarValorLabel(item.id)'>{{item.label}}</li>
</ul>
</template>

<style>
#app {
  font-family:  Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
