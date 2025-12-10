<script setup>
const message = defineModel('message');

const mathage = defineModel('mathage');

const props = defineProps(['messageReception']);

const emit = defineEmits(['update:messageReception']);
</script>

<template>
    <div>
        <input v-model="message" placeholder="Typ iets..." />
    </div>

    <br />

    <div>
        <input v-model="mathage" placeholder="Typ een getal" type="number" />
    </div>

    <br />

    <div>
        <input :value="props.messageReception" @input="emit('update:messageReception', $event.target.value)" />
    </div>
</template>
