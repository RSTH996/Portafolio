<script setup>
import Tarjeta from "./components/Tarjetas/Tarje_Tas.vue";
import Lenguaje from "./components/Tarjetas/Ni_vel.vue";
import Precentacion from "./components/Tarjetas/Precen_tacion.vue";


function Valor() {
    var D1 = document.querySelector(".Lenguaje");
    var B1 = document.querySelector(".liboton");
    var B2 = document.querySelector(".libotonH");    
    if (D1.style.visibility === "visible") {     
        D1.style.marginLeft = "-100%";  
        B1.style.marginLeft = "-100%";
        B2.innerHTML=">>";        
        D1.style.visibility = "hidden"
    } else {                         
        D1.style.marginLeft = "0%";        
        D1.style.visibility = "visible"
        B1.style.marginLeft = "-53%";
        B2.innerHTML="<<";
    }
}
</script>

<template>

    <body class="total">
        <div>
            <div>
                <Lenguaje class="Lenguaje" />
            </div>
        </div>
        <div>
            <button class="liboton" type="button" v-on:click="Valor()"><h3 class="libotonH"><<</h3></button>
        </div>
        <div>
            <Precentacion />
            <Tarjeta />
        </div>
    </body>
</template>

<style>
.total {
    display: grid;
    grid-template-columns: repeat(3, 30%);
}

.Lenguaje{
    transition: all 2s;
}
.liboton {
    grid-column: 1/1;
    margin-left: -53%;
    margin-top: 65%;
    padding-top: 0%;
    height: 300px;
    border-color: beige;
    background-color: burlywood; 
    transition: all 1.4s;   
}
</style>
