<script setup>

import { ref } from 'vue'
const emit = defineEmits(['add'])
const input = ref(null)
const item = ref("")

function onSubmit() {
    if (item.value == "") return;
    emit('add', item.value)
    input.value.reset()
    item.value = ""
}
</script>

<template>
    <form ref="input" @submit.prevent="onSubmit">
        <label for="item">Item: </label>
        <input type="text" id="item" v-model="item" />
        <input type="submit" />
        
    </form>
</template>

<style scoped>
</style>