<script setup lang="ts">
    import * as data from '../assets/data.json';
    import { ref } from 'vue';

    let planet = ref(0);

    function changePlanet (number:number) {
        planet.value = number
    }

</script>

<template>
    <section class="destination">
        <div class="wrapper">
            <p class="heading-xs"><b>01</b> Pick your Destination</p>
            <div class="planet-container">
                <div class="planet-image">
                    <img 
                        :src="data.destinations[planet].images.webp" 
                        :alt="data.destinations[planet].name" 
                    />
                </div>
                <div class="planet-information">
                    <ul>
                        <li 
                            :class="planet === 0 ? 'nav-text active' : 'nav-text'" 
                            @click="changePlanet(0)"
                        >
                            Moon
                        </li>
                        <li 
                            :class="planet === 1 ? 'nav-text active' : 'nav-text'" 
                            @click="changePlanet(1)"
                        >
                            Mars
                        </li>
                        <li 
                            :class="planet === 2 ? 'nav-text active' : 'nav-text'" 
                            @click="changePlanet(2)"
                        >
                            Europa
                        </li>
                        <li 
                            :class="planet === 3 ? 'nav-text active' : 'nav-text'" 
                            @click="changePlanet(3)"
                        >
                            Titan
                        </li>
                    </ul>
                    <p class="heading-l">{{ data.destinations[planet].name }}</p>
                    <p class="text">
                        {{ data.destinations[planet].description }}
                    </p>
                    <hr/>
                    <div class="planet-statistics">
                        <div>
                            <p class="subheading-s">Avg. distance</p>
                            <p class="subheading-l">{{ data.destinations[planet].distance }}</p>
                        </div>
                        <div>
                            <p class="subheading-s">Est. travel time</p>
                            <p class="subheading-l">{{ data.destinations[planet].travel }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
  