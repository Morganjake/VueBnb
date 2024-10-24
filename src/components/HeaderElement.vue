

<template>

<div class="navbar">

    <p class="logo"> VueBnB</p>

    <input type="text" placeholder="Search Your Address" />

    <input type="time" placeholder="Check in" />

    <input type="time" placeholder="Check out" />

</div>

</template>

<script setup>



</script>

<style>

.playwrite-gb-s-logoFont {

    font-family: "Playwrite GB S", cursive;
    font-optical-sizing: auto;
    font-weight:48;
    font-style: normal;

}
body{

    overflow: hidden;
    padding: 0;
    margin: 0;

}

.navbar {

    overflow: hidden;
    display: grid;
    grid-template-rows: auto;
    grid-template-columns: repeat(4, auto);
    grid-template-areas: "logo menus toggler";
    column-gap: 20px;
    position: absolute;
    width: 100%;
    background-color: transparent;
    align-items: center;
    justify-content: space-around;
    margin: 0;
    padding: 0 10px;
    backdrop-filter: blur(100px);


}

.logo {

    display: flex;
    font-size: 34px;
    color: #9AFFF9;
    //padding: 0 15px;
    font-family: "Playwrite GB S", cursive;
    margin: 10px;
    text-align: center;

}

.navbar input[type=text] {

    border: white solid 2px;
    font-family: "Roboto", sans-serif;
    border-radius: 30px;
    padding: 8px;
    font-size: 17px;
    background-color: transparent;
    color: white;
    margin: 0;

}

.roboto-regular {
    font-family: "Roboto", sans-serif;
    font-weight: 400;
    font-style: normal;
}

.navbar input[type=time] {

    display: flex;
    border: white solid 2px;
    border-radius: 30px;
    padding: 8px 2.5pc;
    font-size: 17px;
    background-color: transparent;
    color: white;
    color-scheme: dark;
    margin: 0;


}



</style>

