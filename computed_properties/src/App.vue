<script setup>
import {ref} from 'vue';
const people = ref([
    {name: 'Jodocus', age: 10},
    {name: 'Plubucus', age: 346092},
]);

const newName = ref();
const newAge = ref();
</script>

<template>
    <div>hoi</div>

    <input v-model="newName" />
    {{ newName }}

    <br />
    <br />

    <input v-model="newAge" v-model.number="newAge" />
    {{ newAge }}
</template>

<style scoped></style>
