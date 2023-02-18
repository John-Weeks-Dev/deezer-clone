<script setup>
  import MixesInspiredBy from '../components/MixesInspiredBy.vue';
  import MultiArtistSelect from '../components/MultiArtistSelect.vue';
  import CustomCarousel from '../components/CustomCarousel.vue';
  import Highlights from '../components/Highlights.vue';
</script>

<template>
  <div class="max-w-[1500px] mx-auto">
    <div class="px-8 mt-8 min-w-[800px] w-full">
        <div class="text-white text-xl font-semibold inline-block">
            Mixes inspired by...
            <div class="text-sm font-light text-[#A2A2AD]">Discover new tracks similar to your favourites</div>
        </div>

        <div class="py-3"></div>

        <div class="flex justify-between w-full gap-8">
            <div class="xl:w-1/3 w-1/2">
              <MixesInspiredBy 
                class="pb-1.5"
                text="VAMPIRE (feat. Oli Sykes of Bring Me The Horizon)"
                by="Ic3peak" 
                to="/artist"
                image="https://picsum.photos/id/147/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="Deutchland"
                by="Rammstein" 
                to="/artist"
                image="https://picsum.photos/id/166/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="Fallout"
                by="Masked Wolf" 
                to="/artist"
                image="https://picsum.photos/id/127/300/300"
              />
            </div>
            <div class="xl:w-1/3 w-1/2">
              <MixesInspiredBy 
                class="pb-1.5"
                text="Pray For Plagues"
                by="Bring Me the Horizon" 
                to="/artist"
                image="https://picsum.photos/id/201/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="Candy Truck / You Expected"
                by="Bring Me the Horizon" 
                to="/artist"
                image="https://picsum.photos/id/222/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="L'efant sauvage"
                by="Gojira" 
                to="/artist"
                image="https://picsum.photos/id/212/300/300"
              />
            </div>
            <div class="xl:block hidden xl:w-1/3">
              <MixesInspiredBy 
                class="pb-1.5"
                text="Bad Life"
                by="Sigrid" 
                to="/artist"
                image="https://picsum.photos/id/211/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="Dystopia"
                by="Megadeth" 
                to="/artist"
                image="https://picsum.photos/id/123/300/300"
              />
              <MixesInspiredBy 
                class="pb-1.5"
                text="Can You Feel My Heart"
                by="Bring Me the Horizon" 
                to="/artist"
                image="https://picsum.photos/id/94/300/300"
              />
            </div>
        </div>
    </div>

    <div class="px-8 mt-8 min-w-[800px]">
        <div class="text-white text-xl font-semibold inline-block">
            Made for you
        </div>

        <div class="py-3"></div>

        <div class="flex justify-start gap-7 ">
            <MultiArtistSelect 
              class="w-1/4"
              category="daily" 
              text="Featuring Bring Me the Horizon, Our Last Night, Bad Omens, The Retaliators"
              to="/artist"
              :images="{
                one: 'https://picsum.photos/id/45/300/300',
                two: 'https://picsum.photos/id/55/300/300',
                three: 'https://picsum.photos/id/54/300/300',
                four: 'https://picsum.photos/id/76/300/300',
              }"
            />
            <MultiArtistSelect 
              class="w-1/4"
              category="daily" 
              text="Featuring Metallica, Jessye Norman, Dresdner Philharmonie, San Francisco Symphony"
              to="/artist"
              :images="{
                one: 'https://picsum.photos/id/123/300/300',
                two: 'https://picsum.photos/id/141/300/300',
                three: 'https://picsum.photos/id/111/300/300',
                four: 'https://picsum.photos/id/212/300/300',
              }"
            />
            <MultiArtistSelect 
              class="w-1/4"
              category="daily" 
              text="Featuring Panter, Alden Karik, Arturiko, Krista Masalta"
              to="/artist"
              :images="{
                one: 'https://picsum.photos/id/65/300/300',
                two: 'https://picsum.photos/id/98/300/300',
                three: 'https://picsum.photos/id/78/300/300',
                four: 'https://picsum.photos/id/74/300/300',
              }"
            />
            <MultiArtistSelect 
              class="w-1/4"
              category="daily" 
              text="Featuring Machine Gun Kelly, Girlfriends, Mod Sun, Chri$tian Gate$"
              to="/artist"
              :images="{
                one: 'https://picsum.photos/id/242/300/300',
                two: 'https://picsum.photos/id/121/300/300',
                three: 'https://picsum.photos/id/221/300/300',
                four: 'https://picsum.photos/id/188/300/300',
              }"
            />
        </div>
    </div>

    <div class="px-8 mt-8 min-w-[800px]">
        <div class="py-3"></div>

        <p class="text-center pb-6 text-[#D1D1D6] text-sm">Unlock Flow by selecting your favourite artists for improved recommendations.</p>

        <div class="flex justify-center gap-7 full">
            <div class="flex items-center justify-center relative">
              <img width="100" class="absolute -left-36 rounded-full z-0 cursor-pointer" src="https://picsum.photos/id/188/300/300" />
              <img width="115" class="absolute -left-[80px]  rounded-full z-10 cursor-pointer" src="https://picsum.photos/id/66/300/300" />
              <img width="160" class="rounded-full z-20 cursor-pointer" src="https://picsum.photos/id/144/300/300" />
              <img width="115" class="absolute -right-[80px] rounded-full z-10 cursor-pointer" src="https://picsum.photos/id/141/300/300" />
              <img width="100" class="absolute -right-36 rounded-full z-0 cursor-pointer" src="https://picsum.photos/id/222/300/300" />
            </div>
        </div>
        <div class="w-full flex justify-center p-3">
          <button 
            type="button" 
            class="text-white text-[15px] font-semibold rounded-full bg-[#EF5465] hover:bg-[#d8384a] px-8 py-2 text-center"
          >
            ADD ARTISTS
          </button>
        </div>
    </div>

    <div class="mt-8 min-w-[800px]">
      <CustomCarousel 
        category="New releases for you"
        :data="[
          { url: 'https://picsum.photos/id/89/300/300', song: 'Foregone', by: 'In Flames', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/101/300/300', song: 'Dark Waters', by: 'Delain', releasedOn: '09/01/2023' },
          { url: 'https://picsum.photos/id/121/300/300', song: 'Heritage', by: 'Distant', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/134/300/300', song: 'Meanwhile', by: 'Klone', releasedOn: '08/02/2023' },
          { url: 'https://picsum.photos/id/144/300/300', song: 'Truth Decay', by: 'You Me At Six', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/155/300/300', song: 'This Is Why', by: 'Paramore', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/166/300/300', song: 'The Jaws Of Life', by: 'Pierce The Veil', releasedOn: '09/23/2023' },
          { url: 'https://picsum.photos/id/198/300/300', song: 'The Future Is Your Past', by: 'In The Brian Jonestown Massacre', releasedOn: '07/25/2023' },
          { url: 'https://picsum.photos/id/211/300/300', song: 'The Land, The Water, The Sky', by: 'Black Belt Eagle Scout', releasedOn: '09/22/2023' },
          { url: 'https://picsum.photos/id/223/300/300', song: 'The Day My Father Died', by: 'SYML', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/225/300/300', song: 'Complete Mountain Almanac', by: 'Complete Mountain Almanac', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/239/300/300', song: 'Music From Montana Story', by: 'Kevin Morby', releasedOn: '10/01/2023' },
        ]"
      />
    </div>

    <div class="px-8 mt-8 min-w-[800px]">
      <div class="text-white text-xl font-semibold inline-block">
            Highlights
        </div>

        <div class="py-3"></div>

        <div class="flex items-center gap-8">
          <div class="rounded-lg w-1/2">
            <Highlights 
              by="Some Artist 1"
              song="Awsome Song for you!"
              image="https://picsum.photos/id/220/800/300"
            />
          </div>
          <div class="rounded-lg w-1/2">
            <Highlights 
              by="Some Artist 2"
              song="Another banger BRUV!"
              image="https://picsum.photos/id/229/800/300"
            />
          </div>
        </div>
    </div>

    <div class="mt-8 min-w-[800px]">
      <CustomCarousel 
        category="Popular playlist"
        :data="[
          { url: 'https://picsum.photos/id/54/300/300', song: 'Foregone', by: 'In Flames', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/102/300/300', song: 'Dark Waters', by: 'Delain', releasedOn: '09/01/2023' },
          { url: 'https://picsum.photos/id/126/300/300', song: 'Heritage', by: 'Distant', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/136/300/300', song: 'Meanwhile', by: 'Klone', releasedOn: '08/02/2023' },
          { url: 'https://picsum.photos/id/146/300/300', song: 'Truth Decay', by: 'You Me At Six', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/156/300/300', song: 'This Is Why', by: 'Paramore', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/165/300/300', song: 'The Jaws Of Life', by: 'Pierce The Veil', releasedOn: '09/23/2023' },
          { url: 'https://picsum.photos/id/196/300/300', song: 'The Future Is Your Past', by: 'In The Brian Jonestown Massacre', releasedOn: '07/25/2023' },
          { url: 'https://picsum.photos/id/216/300/300', song: 'The Land, The Water, The Sky', by: 'Black Belt Eagle Scout', releasedOn: '09/22/2023' },
          { url: 'https://picsum.photos/id/222/300/300', song: 'The Day My Father Died', by: 'SYML', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/227/300/300', song: 'Complete Mountain Almanac', by: 'Complete Mountain Almanac', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/237/300/300', song: 'Music From Montana Story', by: 'Kevin Morby', releasedOn: '10/01/2023' },
        ]"
      />
    </div>

    <div class="px-8 mt-8 min-w-[800px]">
      <div class="text-white text-xl font-semibold inline-block">
            Highlights
        </div>

        <div class="py-3"></div>

        <div class="flex items-center gap-8">
          <div class="rounded-lg w-1/2">
            <Highlights 
              by="Some Artist 1"
              song="Awsome Song for you!"
              image="https://picsum.photos/id/177/800/300"
            />
          </div>
          <div class="rounded-lg w-1/2">
            <Highlights 
              by="Some Artist 2"
              song="Another banger BRUV!"
              image="https://picsum.photos/id/126/800/300"
            />
          </div>
        </div>
    </div>

    <div class="mt-8 min-w-[800px]">
      <CustomCarousel 
        category="New releases for you"
        :data="[
          { url: 'https://picsum.photos/id/134/300/300', song: 'Foregone', by: 'In Flames', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/144/300/300', song: 'Dark Waters', by: 'Delain', releasedOn: '09/01/2023' },
          { url: 'https://picsum.photos/id/146/300/300', song: 'Heritage', by: 'Distant', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/78/300/300', song: 'Meanwhile', by: 'Klone', releasedOn: '08/02/2023' },
          { url: 'https://picsum.photos/id/151/300/300', song: 'Truth Decay', by: 'You Me At Six', releasedOn: '10/01/2023' },
          { url: 'https://picsum.photos/id/155/300/300', song: 'This Is Why', by: 'Paramore', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/167/300/300', song: 'The Jaws Of Life', by: 'Pierce The Veil', releasedOn: '09/23/2023' },
          { url: 'https://picsum.photos/id/191/300/300', song: 'The Future Is Your Past', by: 'In The Brian Jonestown Massacre', releasedOn: '07/25/2023' },
          { url: 'https://picsum.photos/id/194/300/300', song: 'The Land, The Water, The Sky', by: 'Black Belt Eagle Scout', releasedOn: '09/22/2023' },
          { url: 'https://picsum.photos/id/177/300/300', song: 'The Day My Father Died', by: 'SYML', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/227/300/300', song: 'Complete Mountain Almanac', by: 'Complete Mountain Almanac', releasedOn: '10/02/2023' },
          { url: 'https://picsum.photos/id/232/300/300', song: 'Music From Montana Story', by: 'Kevin Morby', releasedOn: '10/01/2023' },
        ]"
      />
    </div>

    <div class="pb-40"></div>
  </div>
</template>
