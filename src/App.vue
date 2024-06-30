<script setup lang="ts">
import { RouterLink, RouterView, useRoute } from 'vue-router'
import { ref, watch } from 'vue';

  const idForBG = ref('')
  const route = useRoute()

  function updateBackgroundImage(path:any) {
    idForBG.value = path
  }

  watch(route, (newRoute) => {
    updateBackgroundImage(newRoute.name);
  }, { immediate: true });
  
</script>

<template>
  <div class="background-image" :id="idForBG">
    <header>
      <div class="header-wrapper">
        <img src="./assets/shared/logo.svg" alt="logo"/>
        <div class="header-line"></div>
        <nav>
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
        </nav>
      </div>
    </header>
    <main>
      <RouterView />
    </main>
  </div>
</template>