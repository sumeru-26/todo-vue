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
    <div class="grid grid-cols-3">
    <div></div>
        <div class="fixed inset-x-4 bottom-0 my-4 p-4 justify-center bg-gray-800 rounded-lg">
            <form ref="input" @submit.prevent="onSubmit" class="flex">
                <label for="item" class=" mx-2 font-poppins text-green-500 flex items-center justify-end">Task: </label>
                <input type="text" id="item" v-model="item" class="basis-2/3 grow border-b-2 border-gray-950 focus:border-green-500 outline-none bg-gray-800 text-green-500"/>
                <button @click="onSubmit()" class="group mx-2 p-2 bg-gray-950 hover:bg-green-500 rounded-full flex justify-center items-center">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 stroke-green-500 group-hover:stroke-gray-950">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M12 4.5v15m7.5-7.5h-15" />
                    </svg>
                </button>
            </form>
        </div>
    </div>
</template>

<style scoped>
</style>