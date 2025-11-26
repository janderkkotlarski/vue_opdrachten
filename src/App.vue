<script setup>
import { ref, reactive } from "vue";

const clicks = ref(0);

function incrementClicks() {
  ++clicks.value;
}

const person = reactive({ firstName: "", country: "" });

function changeCountry(newCountry) {
  person.country = newCountry;
}

const tasks = ref([
  { name: "Boodschappen doen", completed: false },
  { name: "Afwassen", completed: true },
  { name: "Hond uitlaten", completed: false },
]);

function completedness(done) {
  return done ? "voltooid" : "niet voltooid";
}

function toggleCompletion(task) {
  task.completed = !task.completed;
}
</script>

<template>
  <button @click="incrementClicks">
    Hoe vaak heb je hier geklikt: {{ clicks }}
  </button>

  <br /><br />

  Naam: {{ person.firstName }}<br />
  Land: {{ person.country }}<br />

  <button @click="changeCountry('Nederland')">Nederland</button>
  <button @click="changeCountry('België')">België</button><br />

  <input v-model.trim="person.firstName" type="text" />

  <ul>
    <li v-for="task in tasks" :key="task.id">
      {{ task.name }} : {{ completedness(task.completed) }} :
      <button @click="toggleCompletion(task)">wissel</button>
    </li>
  </ul>
</template>

<style scoped></style>
