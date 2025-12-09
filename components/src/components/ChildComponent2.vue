<script setup>
import {defineProps, defineEmits} from 'vue';

const props = defineProps(['title']);
const emit = defineEmits(['update:title']);

function updateTitle() {
    emit('update:title', 'Updated Title');
}
</script>

<template>
    <h1>{{ props.title }}</h1>
    <button @click="updateTitle">Update Title</button>
</template>
