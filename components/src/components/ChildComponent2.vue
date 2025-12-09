<script setup>
const message = defineModel();

const mathage = defineModel();
</script>

<template>
    <div>
        <input v-model="message" placeholder="Typ iets..." />
    </div>

    <div>
        <input v-model="mathage" placeholder="Typ een getal" type="number" />
    </div>
</template>
