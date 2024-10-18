<template>
    <h1>Pirate: {{ teamName }}</h1>
    <ul>
        <li v-for="m in members" :key="m.name" >{{ m.name }} ({{ m.role }})</li>
    </ul>
</template>
<script setup lang="ts">
    import { ref } from "vue";
    interface IMember {
        name: string;
        role: string;
    }
    const teamName = "Straw Hats";
    const members = ref<IMember[]>([{
        name: "Luffy", role: 'Captain'
    },{
        name: "Zoro", role: 'Right Hand'
    }])
</script>