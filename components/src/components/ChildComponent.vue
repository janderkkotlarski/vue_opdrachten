<script setup>
import {ref} from 'vue';

defineProps(['message']);

const count = ref(0);
</script>

<template>
    <button @click="++count">Clicked {{ count }} times!</button>
</template>
