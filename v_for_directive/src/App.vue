<script setup>
import {ref} from 'vue';

const tasks = ref([
    {name: 'Boodschappen doen', completed: false},
    {name: 'Afwassen', completed: true},
    {name: 'Hond uitlaten', completed: false},
]);

function completedness(done) {
    return done ? 'voltooid' : 'niet voltooid';
}

function toggleCompletion(task) {
    task.completed = !task.completed;
}
</script>

<template>
    <ul>
        <li v-for="task in tasks" :key="task.id">
            {{ task.name }} : {{ completedness(task.completed) }} :
            <button @click="toggleCompletion(task)">wissel</button>
        </li>
    </ul>
</template>

<style scoped></style>
