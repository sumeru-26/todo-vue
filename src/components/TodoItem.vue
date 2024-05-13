<script setup>
defineProps({
    item: {
        type: String,
        required: true
    },
    index: {
        type: Number,
        required: true
    }
})
</script>

<template>
    <div>
        <span>{{ item }}</span>
        <button @click="$emit('up', item, index)">Up</button>
        <button @click="$emit('down', item, index)">Down</button>
        <button @click="$emit('remove', index)">X</button>
    </div>
</template>