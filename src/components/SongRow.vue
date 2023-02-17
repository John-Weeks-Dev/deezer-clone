<template>
    <li 
        @mouseenter="isHover = true" 
        @mouseleave="isHover = false" 
        class="flex items-center justify-between p-2 hover:bg-[#979797] hover:bg-opacity-5"
    >
        <div class="flex items-center">
            <div class="relative">
                <div 
                    v-if="isHover" 
                    class="p-1 mt-[2px] ml-[3px] absolute rounded-full bg-white cursor-pointer"
                >
                    <Play
                        v-if="!isPlaying"
                        @click="useSong.playOrPauseThisSong(artist, track)"
                    />
                    <Play
                        v-else-if="isPlaying && currentTrack.name !== track.name"
                        @click="useSong.loadSong(artist, track)"
                    />
                </div>
                <div 
                    v-if="track && currentTrack && currentTrack.name === track.name"
                    class="p-1 mt-[2px] ml-[3px] absolute rounded-full bg-white cursor-pointer"
                >
                    <Pause v-if="!isHover && isPlaying" :size="25" @click="useSong.playOrPauseSong()"/>
                    
                </div>
                <div 
                    @mouseenter="isHoverGif = true"
                    @mouseleave="isHoverGif = false"
                    v-if="isPlaying && track && currentTrack && currentTrack.name === track.name" 
                    class="p-1 mt-[2px] ml-[3px] absolute rounded-full bg-white cursor-pointer"
                >
                    <img
                        v-if="!isHoverGif"
                        src="/images/audio-wave.gif"
                    >
                    <Pause v-if="isHoverGif" :size="25" @click="useSong.playOrPauseSong()"/>
                </div>
                <img width="37" class="border border-[#494949]" :src="artist.albumCover">
            </div>
            <div 
                v-if="track"
                :class="track && currentTrack && currentTrack.name === track.name ? 'text-[#EF5464]' : 'text-[#d4d4d4]'"
                class="text-sm pl-4 hover:underline cursor-pointer"
            >
                {{ track.id }}. {{ track.name }}
            </div>
        </div>
        <div class="flex items-center">
            <div 
                v-if="track.lyrics" 
                @click="openLyrics(track, artist)"
                class="rotate-45 rounded-full p-1.5 mr-3 hover:bg-[#979797] hover:bg-opacity-20 cursor-pointer"
            >
                <MicrophoneVariant fillColor="#CCCCCC" :size="21"/>
            </div>
            <div class="rounded-full p-1.5 mr-3 hover:bg-[#979797] hover:bg-opacity-20 cursor-pointer">
                <HeartOutline fillColor="#CCCCCC" :size="21"/>
            </div>
            <div class="rounded-full p-1.5 hover:bg-[#979797] hover:bg-opacity-20 cursor-pointer">
                <DotsHorizontal fillColor="#CCCCCC" :size="21"/>
            </div>
            <div
                v-if="isTrackTime"
                :class="track && currentTrack && currentTrack.name === track.name ? 'text-[#EF5464]' : 'text-[#d4d4d4]'"
                class="text-[13px] pl-10 font-[200] text-[#d4d4d4]"
            >
                {{ isTrackTime }}
            </div> 
        </div>
    </li>
</template>

<script setup>
  import { ref, toRefs, onMounted } from 'vue'
  import artist from '../artist.json'

  import DotsHorizontal from 'vue-material-design-icons/DotsHorizontal.vue';
  import HeartOutline from 'vue-material-design-icons/HeartOutline.vue';
  import MicrophoneVariant from 'vue-material-design-icons/MicrophoneVariant.vue';
  import Play from 'vue-material-design-icons/Play.vue';
  import Pause from 'vue-material-design-icons/Pause.vue';

  import { useSongStore } from '../stores/song'
  import { storeToRefs } from 'pinia';
  const useSong = useSongStore()
  const { audio, isPlaying, currentTrack, isLyrics } = storeToRefs(useSong)

  let isHover = ref(false)
  let isHoverGif = ref(false)
  let isTrackTime = ref('00:00')

  const props = defineProps({ track: Object })
  const { track } = toRefs(props)

  onMounted(() => {
        const audioMeta = new Audio(track.value.path);
        audioMeta.addEventListener('loadedmetadata', () => {
            const duration = audioMeta.duration;
            const minutes = Math.floor(duration / 60);
            const seconds = Math.floor(duration % 60);
            isTrackTime.value = minutes+':'+seconds.toString().padStart(2, '0')
        });
  })

    const openLyrics = (track, artist) => {
        if (audio.value && !audio.value.paused && track.id === currentTrack.value.id) {
            isLyrics.value = true
        } else if (audio.value && audio.value.paused && track.id === currentTrack.value.id) {
            useSong.playOrPauseSong()
            isLyrics.value = true
        } else {
            useSong.playOrPauseThisSong(artist, track)
            setTimeout(() => isLyrics.value = true, 500)
        }
    }
</script>