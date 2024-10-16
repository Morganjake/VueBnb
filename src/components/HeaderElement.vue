

<template>
<head>

    <title>VueBnB</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playwrite+GB+S:ital,wght@0,100..400;1,100..400&display=swap" rel="stylesheet">

</head>
    <body>
        <div class="navbar">

            <div class="logo">

                <p>VueBnB</p>

            </div>


            <input type="text" placeholder="Search Your Address" />

            <input type="time" placeholder="Check in" />

            <input type="time" placeholder="Check out" />



        </div>
    </body>


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
    background-color: #33423E;
    opacity: 50%;
    align-items: center;
    justify-content: space-around;
    margin: 0;
    padding: 0 10px;

}

.logo {
    display: flex;
    font-size: 24px;
    color: #9AFFF9;
    padding: 0 15px;
    font-family: "Playwrite GB S", cursive;

}

.navbar input[type=text] {
    border: #539987 solid 2px;
    border-radius: 10px;
    padding: 8px;
    font-size: 17px;
    background-color: transparent;
    color: white;

}

.navbar input[type=time] {

    display: flex;
    border: #539987 solid 2px;
    border-radius: 10px;
    padding: 8px 2.5pc;
    font-size: 17px;
    background-color: transparent;
    color: white;


}



</style>

