<script setup>

import {defineProps, ref} from "vue"
const props = defineProps({
    homes: {
        required: true,
        type: Array,
    }
})

const house = ref(props.homes[0]["images"][0])

</script>

<template>
    <div id = "backgroundCarousel">
        <img class = "background" :src="house" alt="House">
        <img class = "background" :src="house" alt="House">
        <img class = "background" :src="house" alt="House">
    </div>

    <div class = "cycle" id = "cycleLeft"></div>
    <div class = "cycle" id = "cycleRight"></div>
</template>

<style>

body {
    overflow: hidden;
}

#backgroundCarousel {
    display: flex;
    height: 100%;
    position: absolute;
    left: -54%;
}

.background {
    max-height: 100vh;
    margin: auto;
}


.cycle {
    position: absolute;
    height: 75px;
    width: 75px;
    border-radius: 75px;
    margin: 0 10px;
    background: gray;
    transform: translate(0, -50%);
}

#cycleLeft {
    top: 50%;
    transform: translate(25px, 0);
}

#cycleRight {
    left: 100%;
    top: 50%;
    transform: translate(calc(-100% - 10px), 0);
}

</style>
