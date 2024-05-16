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
    <div class="m-5 px-5 justify-center flex flex-row gap-3 bg-gray-900 rounded-lg">
        <span class="mx-2 grow flex items-center font-poppins text-green-500">{{ index+1 }}. {{ item }}</span>
        <button @click="$emit('up', item, index)" class="group m-2 bg-gray-950 hover:bg-green-500 rounded-full aspect-square size-10 flex justify-center items-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 stroke-green-500 group-hover:stroke-gray-950">
                <path stroke-linecap="round" stroke-linejoin="round" d="M4.5 10.5 12 3m0 0 7.5 7.5M12 3v18" />
            </svg>
        </button>
        <button @click="$emit('down', item, index)" class="group m-2 bg-gray-950 hover:bg-green-500 rounded-full aspect-square size-10 flex justify-center items-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 stroke-green-500 group-hover:stroke-gray-950">
              <path stroke-linecap="round" stroke-linejoin="round" d="M19.5 13.5 12 21m0 0-7.5-7.5M12 21V3" />
            </svg>
        </button>
        <button @click="$emit('remove', index)" class="group m-2 bg-gray-950 hover:bg-green-500 rounded-full aspect-square size-10 flex justify-center items-center">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 stroke-green-500 group-hover:stroke-gray-950">
                <path stroke-linecap="round" stroke-linejoin="round" d="M6 18 18 6M6 6l12 12" />
            </svg>
        </button>
    </div>
</template>