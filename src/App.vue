<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
</script>

<template>
  <div class="background-image" :id="BGurl">
    <header>
      <div class="header-wrapper">
        <img src="./assets/shared/logo.svg" alt="logo"/>
        <div class="header-line"></div>
        <nav>
          <ul>
            <RouterLink to="/" @click="changeBG('home')"><li :class="BGurl === 'home' ? 'active' : null"><b>00</b> HOME</li></RouterLink>
            <RouterLink to="/destination" @click="changeBG('destination')"><li :class="BGurl === 'destination' ? 'active' : null"><b>01</b>DESTINATION</li></RouterLink>
            <RouterLink to="/crew" @click="changeBG('crew')"><li :class="BGurl === 'crew' ? 'active' : null"><b>03</b>CREW</li></RouterLink>
            <RouterLink to="/technology" @click="changeBG('technology')"><li :class="BGurl === 'technology' ? 'active' : null"><b>04</b>TECHNOLOGY</li></RouterLink>
            
          </ul>
        </nav>
      </div>
    </header>
    <main>
      <RouterView />
    </main>
  </div>
  
</template>

<script lang="ts">
export default {
  data() {
    return {
      backgroundImages: {
        home: 'home',
        destination: 'destination',
        crew: 'crew',
        technology: 'technology'
      },
      BGurl: 'home'
    };
  },
  methods: {
    changeBG(currentPage:any) {

      if (currentPage === "home"){
        this.BGurl = this.backgroundImages.home
      }
      if (currentPage === "destination"){
        this.BGurl = this.backgroundImages.destination
      }
      if (currentPage === "crew"){
        this.BGurl = this.backgroundImages.crew
      }
      if (currentPage === "technology"){
        this.BGurl = this.backgroundImages.technology
      }

      // this.BGurl = currentPage
      
    }
  }
};
</script>