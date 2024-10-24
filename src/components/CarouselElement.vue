<script setup>

import {defineProps, ref} from "vue"
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

    // Creating and setting the image
    const img = document.createElement("img")
    img.className = "carouselImage"

    img.src = props.homes[Math.floor(Math.random() * props.homes.length)]["images"][0]

    // Adding and deleting images to carousel
    if (direction === 1) {
        carousel.appendChild(img)
        carousel.removeChild(carousel.firstChild)
    }
    else {
        carousel.insertBefore(img, carousel.firstChild)
        carousel.removeChild(carousel.lastChild)
    }

    // moves the carousel so the middle picture is the same as before pictures were added and deleted
    carousel.style.left = "50vw"
    let offset = window.innerWidth / 2
    offset -= carousel.children[0].getBoundingClientRect().width + carousel.children[1].getBoundingClientRect().width / 2
    if (direction === -1) {
        offset -= carousel.children[1].getBoundingClientRect().width / 2 + carousel.children[2].getBoundingClientRect().width + carousel.children[3].getBoundingClientRect().width / 2
    }
    carousel.style.left = offset + "px"

    // Slides the picture to the next one
    let increment = 0
    if (direction === 1) {
        increment = (carousel.children[1].getBoundingClientRect().width / 2 + carousel.children[2].getBoundingClientRect().width / 2) / -100
    } else {
        increment = (carousel.children[3].getBoundingClientRect().width / 2 + carousel.children[2].getBoundingClientRect().width / 2) / 100
    }

    for (let i = 1; i < 101; i++) {
        setTimeout(_ => {
            // Slide the carousel using an Ease In and Out sin wave
            carousel.style.left = offset + increment * (Math.sin(i * Math.PI / 200) ** 3 * 100) + "px"
        }, i * 4)
    }

    setTimeout(_ => {
        cycleDebounce = false
    }, 400)

}

// Initialises the carousel position
setTimeout(_ => {
    const carousel = document.getElementById("backgroundCarousel")
    console.log(carousel)
    carousel.style.left = "50vw"
    let offset = window.innerWidth / 2
    offset -= carousel.children[1].getBoundingClientRect().width / 2 + carousel.children[2].getBoundingClientRect().width + carousel.children[3].getBoundingClientRect().width / 2
    carousel.style.left = offset + "px"
}, 1)

</script>

<template>
    <div id = "middle"></div>
    <div id="backgroundCarousel">
        <img class="carouselImage" :src="house" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house3" alt="house">
        <img class="carouselImage" :src="house2" alt="house">
        <img class="carouselImage" :src="house" alt="house">
    </div>

    <div class="cycle" id="cycleLeft" @click="cycle(-1)"></div>
    <div class="cycle" id="cycleRight" @click="cycle(1)"></div>
</template>

<style>

#middle {
    position: absolute;
    height: 100vh;
    width: 50vw;
    background-color: whitesmoke;
}

#backgroundCarousel {
    position: absolute;
    display: flex;
    left: 50vw;
}

.carouselImage {
    max-height: 100vh;
    min-height: 100vh;
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
