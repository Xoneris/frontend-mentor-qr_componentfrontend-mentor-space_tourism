<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import { ref, watch } from 'vue';

  const idForBG = ref('')
  const isMobileNavOpen = ref(false)
  const route = useRoute()

  function updateBackgroundImage(path:any) {
    idForBG.value = path
  }

  function openMobileNav(trueOrFalse:boolean) {
    isMobileNavOpen.value = trueOrFalse
  }

  watch(route, (newRoute) => {
    updateBackgroundImage(newRoute.name);
  }, { immediate: true });
  
</script>

<template>
  
    <header>
      <div class="header-wrapper">
        <RouterLink to="/">
          <img src="./assets/shared/logo.svg" alt="logo"/>
        </RouterLink>
        <div class="header-line"></div>
        <nav>
          <ul>
            <RouterLink to="/">
              <li :class="idForBG === 'home' ? 'active' : ''"><b>00</b> HOME</li>
            </RouterLink>
            <RouterLink to="/destination">
              <li :class="idForBG === 'destination' ? 'active' : ''"><b>01</b>DESTINATION</li>
            </RouterLink>
            <RouterLink to="/crew">
              <li :class="idForBG === 'crew' ? 'active' : ''"><b>02</b>CREW</li>
            </RouterLink>
            <RouterLink to="/technology">
              <li :class="idForBG === 'technology' ? 'active' : null"><b>03</b>TECHNOLOGY</li>
            </RouterLink>
          </ul>
        </nav>

        <div class="mobile-nav-container">
          <div class="mobile-burger-menu" @click="openMobileNav(!isMobileNavOpen)">
            <img src="./assets/shared/icon-hamburger.svg" alt="hamburger-icon"/>
          </div>
          <div class="mobile-nav" :id="isMobileNavOpen ? 'open' : 'closed'">
            <div class="mobile-nav-close">
              <img src="./assets/shared/icon-close.svg" alt="hamburger-close-icon" @click="openMobileNav(!isMobileNavOpen)"/>
            </div>
            <ul>
              <RouterLink to="/">
                <li :class="idForBG === 'home' ? 'active' : null"><b>00</b> HOME</li>
              </RouterLink>
              <RouterLink to="/destination">
                <li :class="idForBG === 'destination' ? 'active' : null"><b>01</b>DESTINATION</li>
              </RouterLink>
              <RouterLink to="/crew">
                <li :class="idForBG === 'crew' ? 'active' : null"><b>02</b>CREW</li>
              </RouterLink>
              <RouterLink to="/technology">
                <li :class="idForBG === 'technology' ? 'active' : null"><b>03</b>TECHNOLOGY</li>
              </RouterLink>
            </ul>
          </div>
        </div>
        
      </div>
    </header>
    <main>
      <RouterView />
    </main>
    <div class="background-image" :id="idForBG"></div>
</template>