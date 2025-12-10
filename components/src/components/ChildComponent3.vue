<script setup>
const props = defineProps(['messageInput']);

const emit = defineEmits(['update:messageInput']);
</script>

<template>
    <div>
        <input :value="props.messageInput" @input="emit('update:messageInput', $event.target.value)" />
    </div>
</template>
