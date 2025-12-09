<script setup>
import {ref} from 'vue';
import ChildComponent from './ChildComponent.vue';

const note = ref('test');

const handleMessage = newMessage => {
    note.value = newMessage;
};
</script>

<template>
    <ChildComponent v-model:message="note" @update-message="handleMessage" />

    <div>{{ message }}</div>
</template>
