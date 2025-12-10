<script setup>
import {ref} from 'vue';
import ChildComponent2 from './ChildComponent2.vue';
import ChildComponent3 from './ChildComponent3.vue';

const sharedMessage = ref('');

const sharedMathage = ref('');

const indicator = ref('');

const feedback = ref('');
</script>

<template>
    <ChildComponent2
        v-model:message="sharedMessage"
        v-model:mathage="sharedMathage"
        :messageReception="indicator"
        @update:messageReception="$event => (indicator = $event)"
    />
    <p>Huidig berichten: {{ sharedMessage }} : {{ sharedMathage }} : {{ indicator }}</p>

    <ChildComponent3 :messageInput="feedback" @update:messageInput="$event => (feedback = $event)" />

    <p>{{ feedback }}</p>
</template>
