<script setup lang="ts">
import { ref } from 'vue';
import Booktable from './components/Booktable.vue';
import Bookcard from './components/Bookcard.vue';
import books from "./bookdata"

const tableView = ref(false)
</script>

<template>
  <div class="container">
    <button @click="tableView = !tableView;">
      {{ tableView ? "Switch to card view" : "Switch to table view" }}
    </button>
    <Booktable v-if="tableView" :books="books"/>
    <Bookcard v-else :books="books"/>
  </div>
</template>

<style scoped>
  button {
    background-color: blue;
    color: white;
    border: none;
    border-radius: 5px;
    padding: 8px 16px;
    min-height: 50px;
    max-height: 100px;
    font-size: 14px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  button:hover {
    background-color: darkblue;
  }
</style>
