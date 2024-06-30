<script setup lang="ts">
  import { RouterLink } from 'vue-router';
</script>

<template>
  <section class="home">
    <div class="hero">
      <div class="hero-wrapper">
        <div class="text-wrapper">
        <p class="heading-xs">So, you want to travel to</p>
        <p class="heading-xl">Space</p>
        <p class="text">
          Let’s face it; if you want to go to space, you might as well genuinely go to outer space and not hover kind of on the edge of it. Well sit back, and relax because we’ll give you a truly out of this world experience!
        </p>
      </div>
      <RouterLink to="/destination">
        <div class="call-to-action heading-s">
          Explore
        </div>
      </RouterLink>
      
      </div>
      
    </div>
    
    
  </section>
  
</template>
