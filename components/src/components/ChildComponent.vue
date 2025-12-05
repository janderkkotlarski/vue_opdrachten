<script setup>
defineProps(['note']);

const emit = defineEmits(['updateMessage']);

const emitEvent = () => {
    emit('updateMessage', 'Kindcomponent terugkoppeling');
};
</script>

<template>
    <div>{{ note }}</div>

    <button @click="emitEvent">Pro-Beer</button>
</template>
