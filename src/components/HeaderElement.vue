

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

            <div class="searchAddress">

                <input type="text" placeholder="Search Your Address" />

            </div>

            <div class="searchContainer">

                <input type="time" placeholder="Check in" />

                <input type="time" placeholder="Check out" />


            </div>

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

    display: flex;
    position: absolute;
    height: 15%;
    width: 100%;
    background-color: #33423E;
    opacity: 50%;
    align-items: center;
    justify-content: space-between;
    margin: 0;

}

.logo {
    display: flex;
    font: 48px playwrite, serif;
    font-style: normal;
    color: #9AFFF9;
    padding: 10px;

}

.navbar input[type=text] {
    border: #539987 solid 2px;
    border-radius: 10px;
    padding: 8px;
    font-size: 17px;
    background-color: transparent;
    color: white;
    justify-content: right;

}

.searchContainer{

    display: flex;
    justify-content: space-around;
    align-items: center;

}

.searchContainer input{

    display: flex;
    border: #539987 solid 2px;
    border-radius: 10px;
    padding: 8px;
    font-size: 17px;
    background-color: transparent;
    color: white;
    padding-right: 5pc;


}



</style>

