<template>
    <header class="mt-5">
        <h1 class="text-4xl font-bold text-sky-900">Wonderfull CountDown</h1>
    </header>
    <div class="flex flex-row self-center justify-around w-3/12 flex-wrap mt-5">
        <p class="max-w-full min-w-full font-extrabold m-3">Time left:</p>
        <div class="flex flex-col">
            <span class="duration">{{ days }}</span>
            <span class="duration-title">days</span>
        </div>
        <span class="m-0">:</span>
        <div class="flex flex-col">
            <span class="duration">{{ hours }}</span>
            <span class="duration-title">hours</span>
        </div>
        <span class="m-0">:</span>
        <div class="flex flex-col">
            <span class="duration">{{ minutes }}</span>
            <span class="duration-title">minutes</span>
        </div>
        <span class="m-0">:</span>
        <div class="flex flex-col">
            <span class="duration">{{ seconds }}</span>
            <span class="duration-title">seconds</span>
        </div>
    </div>
</template>

<script setup lang="ts">
    import { ref } from 'vue'

    const days = ref(0)
    const hours = ref(0)
    const minutes = ref(0)
    const seconds = ref(0)
</script>

<style scoped>

</style>