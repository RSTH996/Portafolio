<script setup>
import { ref } from "vue";
import { Habilidades, Datos } from "../Informacion/Dato.js";

let $Boton = ref("<<")
function Valor() {     
    var D1 = document.querySelector(".Conocimiento");
    var B1 = document.querySelector(".liboton");
    if (this.$Boton === "<<") {     
        D1.style.marginLeft = "-55%";  
        B1.style.marginLeft = "30%"
        this.$Boton=">>";   
    } else {                         
        D1.style.marginLeft = "0%";     
        B1.style.marginLeft = "15%";
        this.$Boton="<<";  
    }
}
</script>

<template>
    <div class="Conocimiento">
        <ul v-for="D in Datos" v-bind:key="D">
            <li v-for=" (I, index) in Habilidades" :key="index">
                <img v-if=I.N height="55px" width="70px" :src=D.Carpeta+I.L+D.ArchivoB />
                <p>{{ I.L }}</p>
            </li>
        </ul>
        <button class="liboton" type="button" v-on:click="Valor()"><h3>{{ $Boton }}</h3></button>
    </div>
</template>

<style>
.Conocimiento {
    display: flex;
    background-color: beige;
    width: 290px;
    height: 100%;
    text-align: center;        
    transition: all 1.5s;
}

.Conocimiento h2 {
    margin-left: -25%;
    padding: 10%;
}

/*Lista e conocimiento */
li {
    display: grid;
    grid-template-columns: repeat(2, 6rem);
    padding-bottom: 15%;
    font-family: Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
    font-size: x-large;
}

/*Boton */
.liboton {  
    margin-left: 15%;
    margin-top: 85%;
    padding-top: 0%;
    height: 400px;
    border-color: beige;
    background-color: burlywood; 
    border-top-right-radius: 40%;
    border-bottom-right-radius: 40%;
    border-bottom-left-radius: 10%;
    border-top-left-radius: 10%;
    transition: 1s;    
}
</style>