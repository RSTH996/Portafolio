<script setup>
import { Habilidades, Datos } from "../Informacion/Dato.js";


</script>

<template>
    <div class="Conocimiento">
        <ul v-for="D in Datos" v-bind:key="D">
            <h2>Conocimiento</h2>
            <li v-for=" (I, index) in Habilidades" :key="index">
                <img height="55px" width="70px" :src=D.Carpeta+I.L+D.ArchivoB />
                <p>{{ I.L }}</p>
            </li>
        </ul>
    </div>
</template>

<style>
.Conocimiento {
    display: flex;
    background-color: beige;
    width: 290px;
    height: 100%;
    text-align: center;    
}

.Conocimiento h2 {
    margin-left: -25%;
    padding: 10%;
}

li {
    display: grid;
    grid-template-columns: repeat(2, 6rem);
    padding-bottom: 15%;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: x-large;
}
</style>