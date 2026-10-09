<script setup>
defineProps(['name', 'image', 'source', 'demo'])
</script>
<template>
    <div class="rounded-3xl bg-gray-100 p-8 border">
        <div class="overflow-hidden h-[300px] rounded-3xl mx-auto">
            <img :src="image" class="object-cover w-full h-full rounded-4xl"/>
        </div>
        <h1 class="text-2xl font-bold mt-4 text-gray-700 text-center">{{ name }}</h1>
        <div class="mt-4 flex justify-center gap-5">
            <button class="px-7 py-2 border text-gray-700 bg-white rounded-2xl text-md font-bold hover:bg-gray-700 hover:text-white hover:transition hover:duration-300 hover:ease-in-out cursor-pointer">
                <a target="_blank" :href="source">Github</a>
            </button>
            <button v-if="demo" class="px-7 py-2 border text-gray-700 bg-white rounded-2xl text-md font-bold hover:bg-gray-700 hover:text-white hover:transition hover:duration-300 hover:ease-in-out cursor-pointer">
                <a target="_blank" :href="demo">Live Demo</a>
            </button>
        </div>
    </div>
</template>