<script setup>
defineProps(['message']);

const emit = defineEmits(['updateMessage']);

const emitEvent = () => {
    emit('updateMessage', 'Kindcomponent terugkoppeling');
};
</script>

<template>
    <div>{{ message }}</div>

    <button @click="emitEvent">Probeer</button>
</template>
