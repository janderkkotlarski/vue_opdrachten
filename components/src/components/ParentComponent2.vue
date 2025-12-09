<script setup>
import {ref} from 'vue';
import ChildComponent2 from './ChildComponent2.vue';

const sharedMessage = ref('');

const sharedMathage = ref('');
</script>

<template>
    <ChildComponent2 v-model="sharedMessage" />
    <p>Huidig bericht: {{ sharedMessage }}</p>
    <ChildComponent2 v-model="sharedMathage" />
    <p>Huidig bericht: {{ sharedMathage }}</p>
</template>
