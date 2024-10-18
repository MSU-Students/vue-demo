<script setup lang="ts">
  import { ref } from "vue";
  const counter = ref(1);
  const formTitle = 'Demo lang to';
</script>

<template>
  <header>
    <h1>Practice Pirate</h1>
  </header>
  <main>
    {{ formTitle }}
    {{ counter }}
    <input type="text" v-model="counter" />
    <button @click="counter++">Increment</button>
    <button @click="counter--">Decrement</button>
  </main>
</template>