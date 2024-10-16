<script setup>
import CarouselElement from "@/components/CarouselElement.vue";

import homes from "../json/homes.json"

</script>

<template>

    <HeaderElement>



    </HeaderElement>

    <CarouselElement :homes="homes"></CarouselElement>
</template>

<style>

body {
    margin: 0;
}

</style>

<script setup>

import HeaderElement from '@/components/HeaderElement.vue'

</script>
