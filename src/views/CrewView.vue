<script setup lang="ts">
    import * as data from '../assets/data.json';
    import { ref } from 'vue';

    const crewMember = ref(0);

    function changeCrewMember (number:number) {
        crewMember.value = number
    }

</script>

<template>
    <section class="crew">
      <div class="wrapper">
        <p class="heading-xs"><b>02</b> Meet your crew</p>
        <div class="crew-container-all">
          <div class="crew-container-left">

            <div class="crew-description">
              <p class="heading-s" style="opacity: 0.5">{{ data.crew[crewMember].role }}</p>
              <p class="heading-m">{{ data.crew[crewMember].name }}</p>
              <p class="text">{{ data.crew[crewMember].bio }}</p>
            </div>

            <div class="crew-nav">
              <ul>
                <li 
                  @click="changeCrewMember(0)" 
                  :id="crewMember === 0 ? 'active' : ''"
                >
                  <div class="pagination-icon"></div>
                </li>
                <li 
                  @click="changeCrewMember(1)"
                  :id="crewMember === 1 ? 'active' : ''"
                >
                  <div class="pagination-icon"></div>
                </li>
                <li 
                  @click="changeCrewMember(2)"
                  :id="crewMember === 2 ? 'active' : ''"
                >
                  <div class="pagination-icon"></div>
                </li>
                <li 
                  @click="changeCrewMember(3)"
                  :id="crewMember === 3 ? 'active' : ''"
                >
                  <div class="pagination-icon"></div>
                </li>
              </ul>
            </div>

          </div>
          <div class="crew-image">
            <img 
                :src="data.crew[crewMember].images.webp" 
                :alt="data.crew[crewMember].name" 
            />
          </div>
        </div>
      </div>
    </section>
</template>
  