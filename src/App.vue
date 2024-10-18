<script setup lang="ts">
  import { ref } from "vue";
  import PirateComp from './components/PirateComp.vue';

  const counter = ref(1);
  const formTitle = 'Demo lang to';
</script>

<template>
  <header>
    <h1>Practice </h1>
  </header>
  <main>
    {{ formTitle }}
    <pirate-comp/>    
  </main>
</template>