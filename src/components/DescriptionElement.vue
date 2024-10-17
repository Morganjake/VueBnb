<template>

<div class="container"></div>

<div class="description">

    <p class="title">A Quiet House in the Middle of Nowhere</p>

    <p class="address">302 Hanson Ranch Rd Beaver Creek Colorado USA</p>

    <p class="info">7 guests · 3 beds · 4 rooms</p>

    <p class="rating">☆ 875</p>

</div>



</template>

<style>

.container {

    justify-content: left;
    background-color: #2D3634;
    position: absolute;
    border-radius: 30px;
    opacity: 40%;

    width: 100%;
    padding: 5px 25px;
    bottom: 20px;
    left: 20px;
    max-width: 30pc;
    height: 100%;
    max-height: 13.5rem;

}

.description{

    display: grid;
    grid-template-columns: [line1] 80% [line2] 20%;
    grid-template-rows: auto 30% 30%;
    grid-template-areas:
        "title title"
        "address address"
        "info rating";

    color: white;
    position: absolute;
    border-radius: 30px;
    background-color: transparent;

    padding: 5px 25px;
    bottom: 20px;
    left: 20px;
    width: 100%;
    max-width: 30pc;
    height: 100%;
    max-height: 14rem;

    font-family: "Roboto", sans-serif;
    backdrop-filter: blur(50px);
    opacity: 80%;
}

.title{

    font-size: 1.6rem;
    grid-area: title;
    text-align: center;

    color: #9AFFF9;


}

.info{

    grid-area: info;
    text-align: center;
    font-size: 1.4rem;
    margin: 0;

}

.rating{

    grid-area: rating;
    text-align: right;
    font-size: 1.5rem;
    margin: 0;

}

.address{

    grid-area: address;
    text-align: center;
    font-size: 1.2rem;
    margin: 0;

}

.roboto-regular {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-style: normal;
}

</style>

<script setup>



</script>
