<script setup>
import {ref} from 'vue';
import ChildComponent from './ChildComponent.vue';

const note = ref('');

const handleMessage = newMessage => {
    note.value = newMessage;
};
</script>

<template>
    <ChildComponent message="test?" @update-message="handleMessage" />

    <p>Kindcomponent bericht: {{ note }}</p>
</template>
