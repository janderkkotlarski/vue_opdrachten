<script setup>
import {ref} from 'vue';
import ChildComponent2 from './ChildComponent2.vue';

const title = ref('Initial Title');
</script>

<template>
    <ChildComponent2 v-model:title="title" />
</template>
