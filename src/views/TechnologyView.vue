<script setup lang="ts">
    import * as data from '../assets/data.json';
    import { useWindowSize } from '@vueuse/core'
    import { ref, Transition } from 'vue';

    const technology = ref(0);

    function changetechnology (number:number) {
        technology.value = number
    }

    const { width } = useWindowSize()

</script>


<template>
    <section class="technology">
        <div class="wrapper">
            <p class="heading-xs"><b>03</b> Space launch 101</p>
            <Transition name="fade" mode="out-in">
            <div class="technology-container" :key="data.technology[technology].name">
                <div class="technology-container-left">
                    <div class="technology-nav">
                        <ul>
                            <li
                                @click="changetechnology(0)"
                            >
                                <div :class="technology === 0 ? 'nav-element-active' : 'nav-element'">
                                    <p class="heading-s">1</p>
                                </div>
                            </li>
                            <li
                                @click="changetechnology(1)"
                            >
                                <div :class="technology === 1 ? 'nav-element-active' : 'nav-element'">
                                    <p class="heading-s">2</p>
                                </div>
                            </li>
                            <li
                                @click="changetechnology(2)"
                            >
                                <div :class="technology === 2 ? 'nav-element-active' : 'nav-element'">
                                    <p class="heading-s">3</p>
                                </div>
                            </li>
                        </ul>
                    </div>
                    <div class="technology-description">
                        <p class="heading-s" style="opacity: 0.5">The Terminology...</p>
                        <p class="heading-m">{{ data.technology[technology].name }}</p>
                        <p class="text">{{ data.technology[technology].description }}</p>
                    </div>
                </div>

                <div class="technology-image">
                    <img
                        v-if="width >= 768"
                        :src="data.technology[technology].images.portrait"
                        :alt="data.technology[technology].name"
                    />
                    <img
                        v-else
                        :src="data.technology[technology].images.landscape"
                        :alt="data.technology[technology].name"
                    />
                </div>
            </div>
            </Transition>
        </div>
    </section>
</template>
  