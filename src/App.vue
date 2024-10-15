<script setup>
let homes = await fetch("./json/homes.json")
let json = await homes.json()
console.log(json)
</script>

<template>
    <div>fghfg</div>
</template>

<style>
div {
    font-size: 100px;
}
</style>

