<template>
    <div 
        :id="time" 
        class="my-10 text-white opacity-100"
        :class="{'opacity-30': lyricsPosition !== time}"
    >
        <div v-if="words === 'INSTRAMENTAL SECTION'" class="flex w-full">
            <GuitarElectric :size="200" class="mx-auto"/>
        </div>
        <div v-if="words !== 'INSTRAMENTAL SECTION'">{{ words }}</div>
    </div>
</template>

<script setup>
  import { toRefs, watch } from 'vue'
  import lyrics from '../lyrics.json'
  import GuitarElectric from 'vue-material-design-icons/GuitarElectric.vue'

  import { useSongStore } from '../stores/song'
  import { storeToRefs } from 'pinia';
  const useSong = useSongStore()
  const { trackTime, currentTrack, lyricsPosition } = storeToRefs(useSong)

  const props = defineProps({ time: String, words: String })
  const { time, words } = toRefs(props)

  watch(() => trackTime.value, (trackTime) => {
    setTimeout(() => {
        lyrics[currentTrack.value.id].forEach(res => {
            if (res.time == trackTime) lyricsPosition.value = res.time
        })
    }, 1000)
  })
</script>