<script setup>
import {ref, reactive} from 'vue';

const clicks = ref(0);

function incrementClicks() {
    ++clicks.value;
}

const person = reactive({firstName: '', country: ''});

function changeCountry(newCountry) {
    person.country = newCountry;
}
</script>

<template>
    <button @click="incrementClicks">Hoe vaak heb je hier geklikt: {{ clicks }}</button>

    <br />
    <br />

    Naam: {{ person.firstName }}
    <br />
    Land: {{ person.country }}
    <br />

    <button @click="changeCountry('Nederland')">Nederland</button>
    <button @click="changeCountry('België')">België</button>
    <br />

    <input v-model.trim="person.firstName" type="text" />
</template>

<style scoped></style>
