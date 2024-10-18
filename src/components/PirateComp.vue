<template>
    <h1>Pirate: {{ teamName }}</h1>
    <div>
        <input type="text" v-model="newMember.name" placeholder="Name" />
        <input type="text" v-model="newMember.role" placeholder="Role" />
        <button @click="onRegister">Register</button>
    </div>
    <ul>
        <li v-for="m in members" :key="m.name" >
            {{ m.name }} ({{ m.role }})
            <button @click="onDelete(m.name)">delete</button>
        </li>
    </ul>
</template>
<script setup lang="ts">
    import { ref } from "vue";
    interface IMember {
        name: string;
        role: string;
    }
    const newMember = ref<IMember>({
        name: '', role: ''
    });
    const teamName = "Straw Hats";
    const members = ref<IMember[]>([{
        name: "Luffy", role: 'Captain'
    },{
        name: "Zoro", role: 'Right Hand'
    }])
    function onRegister() {
        members.value.push({...newMember.value});
        newMember.value.name = '';
        newMember.value.role = '';
    }
    function onDelete(name: string) {
        const index = members.value.findIndex((m) => (m.name == name));
        if (index >= 0) {
            members.value.splice(index, 1);
        }
    }
</script>