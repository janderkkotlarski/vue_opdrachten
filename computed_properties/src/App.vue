<script setup>
import {ref, computed} from 'vue';
const people = ref([
    {id: 1, name: 'Jodocus', age: 10},
    {id: 2, name: 'Plubucus', age: 346092},
]);

const newName = ref('');
const newAge = ref('');

function addPerson() {
    // Only add if both fields contain something
    if (newName.value != '' && newAge.value != '') {
        // .value because of ref
        people.value.push({id: people.value.length + 1, name: newName.value, age: newAge.value});
    }

    // Always flush the submitted results
    newName.value = '';
    newAge.value = '';
}

const children = computed(() => {
    return [...people.value].filter();
});
</script>

<template>
    <form>
        <!-- type="text" pro forma -->
        <input v-model="newName" type="text" />
        {{ newName }}

        <br />
        <br />

        <!-- .number for safe conversion, type="number" to allow only numerical input -->
        <input v-model.number="newAge" type="number" />
        {{ newAge }}

        <br />
        <br />

        <!-- .prevent in order to not reload the page -->
        <button @click.prevent="addPerson">Durf je te klikken?</button>
    </form>

    <ul>
        <li v-for="(person, index) in people" :key="person.id">
            {{ person.id }} : {{ person.name }} : {{ person.age }}
        </li>
    </ul>
</template>

<style scoped></style>
