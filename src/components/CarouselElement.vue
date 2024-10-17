<script setup>

import {defineProps, getTransitionRawChildren, ref} from "vue"
const props = defineProps({
    homes: {
        required: true,
        type: Array,
    }
})

const house = ref(props.homes[0]["images"][0])
const house2 = ref(props.homes[1]["images"][0])
const house3 = ref(props.homes[2]["images"][0])
let cycleDebounce = false
let totalClicks = 0 // Total amount of times gone right - total amount of times gone left, used to set randomness

const cycle = (direction) => {

    if (cycleDebounce) {
        return
    }

    const carousel = document.getElementById("backgroundCarousel")
    cycleDebounce = true

    for (let i = 0; i < 2; i++) {
        // Creating and setting the image
        const img = document.createElement("img")
        img.className = "carouselImage"

        img.src = props.homes[Math.floor(Math.random() * props.homes.length)]["images"][0]

        // Adding image to carousel
        if (i === 0) {
            carousel.appendChild(img)
        }
        else {
            carousel.insertBefore(img, carousel.firstChild)
        }
    }

    let offset = carousel.children[3].getBoundingClientRect().width / 2
    if (direction === 1) {
        totalClicks += 1
        offset += carousel.children[4].getBoundingClientRect().width / 2
        offset *= -1
    }
    else {
        totalClicks -= 1
        offset += carousel.children[2].getBoundingClientRect().width / 2
    }

    const finalPosition = window.innerWidth / 2.0 + offset
    const increment = offset / 100.0
    const carouselPos = carousel.getBoundingClientRect().left + carousel.getBoundingClientRect().width / 2

    for (let i = 1; i < 101; i++) {
        setTimeout(_ => {
            carousel.style.left = carouselPos + increment * (Math.sin(i * Math.PI / 200) ** 3 * 100) + "px"
        }, i * 7)
    }

    setTimeout(_ => {

        let offset = carousel.getBoundingClientRect().width / 2

        for (let i = 0; i < 2; i++) {
            if (direction === 1) {
                offset += carousel.children[0].getBoundingClientRect().width / 2
                carousel.removeChild(carousel.firstChild)
            } else {
                offset -= carousel.children[carousel.children.length - 1].getBoundingClientRect().width / 2
                carousel.removeChild(carousel.children[carousel.children.length - 1])
            }
        }

        carousel.style.left = offset + "px"
        cycleDebounce = false
    }, 707)
}

</script>

<template>
    <div id="backgroundCarousel">
        <img class="carouselImage" :src="house" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house" alt="house">
        <img class="carouselImage" :src="house" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house3" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house3" alt="house">
        <img class="carouselImage" :src="house" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house" alt="house">
    </div>

    <div class="cycle" id="cycleLeft" @click="cycle(-1)"></div>
    <div class="cycle" id="cycleRight" @click="cycle(1)"></div>
</template>

<style>

#backgroundCarousel {
    position: absolute;
    display: grid;
    grid-template-columns: auto auto auto auto auto auto auto auto auto auto auto auto auto auto auto;
    top: 85%;
    left: 50%;
    transform: translate(-50%, 0px);
}

.carouselImage {
    max-height: 10vh;
    min-height: 10vh;
    margin: 0;

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
    transform: translate(calc(-100% - 35px), 0);
}

</style>
