<template>
<div>
  <h1>My Shopping list</h1>

  <input type="text" v-model="newItem" id="input" placeholder="Enter item name"/>
  <input type="submit" id="submit" @click="addItem"/>
  <ul>
    <li v-for="item, index in items" :key="index">{{ item }}</li>
  </ul>
</div>
</template>

<script setup>
import { ref } from 'vue'

const newItem = ref();
const items = ref([])

function addItem () {
  items.value.push(newItem.value)
}


</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin: 60px auto;
  }

  ul {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-size: 2rem;
  }
</style>
