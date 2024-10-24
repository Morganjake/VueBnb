<script setup>
import CarouselElement from "@/components/CarouselElement.vue";
import HeaderElement from '@/components/HeaderElement.vue'
import DescriptionElement from '@/components/DescriptionElement.vue'
import DetailedViewElement from '@/components/DetailedViewElement.vue'

import homes from "../json/homes.json"

</script>

<template>

    <CarouselElement :homes="homes"></CarouselElement>
    <HeaderElement></HeaderElement>
    <DescriptionElement :homes="homes"></DescriptionElement>
    <detailed-view-element></detailed-view-element>

</template>

<style>

body {
    margin: 0;
}

</style>

