<script setup>
import CarouselElement from "@/components/CarouselElement.vue";

import homes from "../json/homes.json"

</script>

<template>
    <CarouselElement :homes="homes"></CarouselElement>
</template>

<style>

body {
    margin: 0;
}

</style>

