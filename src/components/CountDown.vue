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
    import { onMounted, onUnmounted, ref } from 'vue'

    const countEnd = new Date();
    countEnd.setMonth(countEnd.getMonth() + 2)
    countEnd.setHours(12)
    countEnd.setMinutes(0)
    countEnd.setSeconds(0)

    const days = ref(0)
    const hours = ref(0)
    const minutes = ref(0)
    const seconds = ref(0)

    var count = 0

    function displayCount() {
        const currentDate = new Date()
        const timeDiff = countEnd.getTime() - currentDate.getTime()
        if(timeDiff < 0 && count != null) {
            clearInterval(count)
        }
        console.log("coucou");
        var distance = timeDiff
        days.value = Math.floor(distance / (1000 * 60 * 60 * 24))
        distance = distance % (1000 * 60 * 60 * 24)
        hours.value = Math.floor(distance / (1000 * 60 * 60))
        distance = distance % (1000 * 60 * 60)
        minutes.value = Math.floor(distance / (1000 * 60))
        distance = distance % (1000 * 60)
        seconds.value = Math.floor(distance / (1000))
        distance = distance % (1000)
    }

    onMounted(() => {
        count = setInterval(() => {
            displayCount()
        }, 1000)
    })

    onUnmounted(() => {
        count = 0
    })
</script>

<style scoped>

</style>