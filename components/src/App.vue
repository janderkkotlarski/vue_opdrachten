<script setup>
import {ref} from 'vue';
import ChildComponent from './components/ChildComponent.vue';

const message = ref('');

const handleMessage = newMessage => {
    message.value = newMessage;
};
</script>

<template>
    <ChildComponent note="test?" @update-message="handleMessage" />

    <p>Kindcomponent bericht: {{ message }}</p>
</template>

<style scoped></style>
