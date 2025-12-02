<script setup>
import {ref, computed} from 'vue';
let ident = 0;

// Make empty people array
const people = ref([]);

// Automatic testing with random generation
// Mostly in order to understand how ref works, how arrays work
// How to use automation and array pushing, the works
function generatePerson() {
    const ident = people.value.length + 1;

    const person = {
        id: ident,
        name: 'Adama_' + ident.toString(),
        age: Math.floor(100 * Math.random() * Math.random()) + 1,
    };

    return person;
}

// Value is important in the setup
function pushPerson() {
    people.value.push(generatePerson());
}

// Variable amount of people
const amount = 5 + Math.floor(10 * Math.random());

// Pushing into the people array
function pushPersons() {
    for (let i = 0; i < amount; ++i) {
        pushPerson();
    }
}

pushPersons();

const newName = ref('');
const newAge = ref('');

function addPerson() {
    // Only add if both fields contain something

    if (newName.value != '' && newAge.value > 0) {
        // .value because of ref
        people.value.push({id: people.value.length + 1, name: newName.value, age: newAge.value});
    }

    // Always flush the submitted results
    newName.value = '';
    newAge.value = '';
}

const ageLimit = 18;

const children = computed(() => {
    return people.value.filter(person => person.age < ageLimit);
});

const adults = computed(() => {
    return people.value.filter(person => person.age >= ageLimit);
});

const peopleCount = computed(() => {
    return people.value.length;
});

const childrenCount = computed(() => {
    return children.value.length;
});

const adultsCount = computed(() => {
    return adults.value.length;
});
</script>

<template>
    <form>
        <!-- type="text" pro forma -->
        <b>Naam</b>
        <br />
        <input v-model="newName" type="text" />
        {{ newName }}

        <br />
        <br />

        <!-- .number for safe conversion, type="number" to allow only numerical input -->
        <b>Leeftijd</b>
        <br />
        <input v-model.number="newAge" type="number" />
        {{ newAge }}

        <br />
        <br />

        <!-- .prevent in order to not reload the page -->
        <button @click.prevent="addPerson">Toevoegen</button>
    </form>

    <ul>
        <b>{{ peopleCount }} Mensen [ Naam : Leeftijd ]</b>
        <li v-for="person in people" :key="person.id">[ {{ person.name }} : {{ person.age }} ]</li>
    </ul>

    <ul>
        <b>{{ childrenCount }} Kinderen [ Naam : Leeftijd ]</b>
        <li v-for="person in children" :key="person.id">[ {{ person.name }} : {{ person.age }} ]</li>
    </ul>

    <ul>
        <b>{{ adultsCount }} Volwassenen [ Naam : Leeftijd ]</b>
        <li v-for="person in adults" :key="person.id">[ {{ person.name }} : {{ person.age }} ]</li>
    </ul>
</template>

<style scoped></style>
