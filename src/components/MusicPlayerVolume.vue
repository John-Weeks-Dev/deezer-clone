<script setup>
import { ref, onMounted, watch } from 'vue'

import { useSongStore } from '../stores/song'
import { storeToRefs } from 'pinia';
const useSong = useSongStore()
const { audio, currentVolume } = storeToRefs(useSong)

let isHover = ref(false)
let volume = ref(null)

onMounted(() => {
    volume.value.addEventListener("input", (e) => {
        audio.value.volume = e.currentTarget.value / 100;
    });
})

watch(() => audio.value, () => {
    setTimeout(() => audio.value.volume = currentVolume.value / 100 ,200)
})
</script>

<template>
    <div
        class="flex items-center ml-2 w-[150px] relative mt-2 mb-[23px]"
        @mouseenter="isHover = true"
        @mouseleave="isHover = false"
    >
        <input
            v-model="currentVolume"
            ref="volume"
            type="range"
            class="
                mt-[24px]
                absolute
                rounded-full
                my-2
                w-full
                h-0
                z-40
                appearance-none
                bg-opacity-100
                focus:outline-none
                accent-white
                cursor-pointer
            "
            :class="
                { 'rangeDotHidden': !isHover },
                { 'rangeDot': isHover }
            "
        >
        <div
            class="pointer-events-none mt-[6px] absolute h-[4px] z-10 inset-y-0 left-0 w-0 bg-white"
            :style="`width: ${currentVolume}%;`"
        />
        <div class="absolute h-[4px] z-[-0] mt-[6px] inset-y-0 left-0 w-full bg-gray-500 rounded-full" />
    </div>
</template>

<style>
.rangeDotHidden[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none;
  appearance: none;
  width: 0;
  height: 0;
}
</style>