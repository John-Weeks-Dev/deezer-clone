<template>
    <RouterLink to="/artist" class="cursor-pointer">
        <div
            class="relative"
            @mouseenter="isHover = true" 
            @mouseleave="isHover = false"
        >
            <div 
                :class="isHover ? 'transition ease-in duration-150 bg-opacity-30' : 'transition ease-out duration-150 bg-opacity-5'"
                class="absolute w-full h-full bg-black z-10 rounded-md"
            />
            <div class="absolute z-50 pl-4 pt-4">
                <div class="bg-black bg-opacity-40 rounded-md text-white px-2 py-1 text-sm text-center inline-block">Album</div>
                <div class="text-white text-xl mt-2 font-[700]">{{ by }}</div>
                <div class="text-white mt-2 font-[400]">{{ song }}</div>
            </div>
            <div class="absolute z-50 bottom-3 left-3 rounded-full bg-white p-1.5">
                <Play :size="27"/>
            </div>
            <img class="rounded-lg" :src="image">
        </div>
    </RouterLink>
</template>

<script setup>
  import { ref } from 'vue'
  import { RouterLink } from 'vue-router'
  import Play from 'vue-material-design-icons/Play.vue'
  let isHover = ref(false)
  const props = defineProps({ by: String, song: String, image: String })
</script>