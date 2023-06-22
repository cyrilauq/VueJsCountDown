<template>
    <div class="flex flex-row self-center justify-center">
        <div class="flex flex-col">
            <span class="duration">{{ days }}</span>
            <span class="duration-title">days</span>
        </div>
        <div class="flex flex-col">
            <span class="duration">{{ hours }}</span>
            <span class="duration-title">hours</span>
        </div>
        <div class="flex flex-col">
            <span class="duration">{{ minutes }}</span>
            <span class="duration-title">minutes</span>
        </div>
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