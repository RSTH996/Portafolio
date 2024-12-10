<script setup>
import { SobreMi } from "../Informacion/Páginas.js";
import { Datos } from "../Informacion/Dato.js";
</script>

<template>
    <div v-for="D in Datos" v-bind:key="D" class="InformacionP">
        <article v-for="SM in SobreMi" v-bind:key="SM">
            <div class="InfoUno">            
            <h1>{{ SM.InicioUno }}</h1>      
            <h1>{{ SM.InicioDos }}</h1>
            <h3>{{ SM.Detalle }}</h3>            
            </div>            
            <img class="InfoDos" height="300px" width="260px" :src=D.Carpeta+SM.imagen1+D.ArchivoA />
        </article>        
    </div>
  </template>

<style>
    .InformacionP{
        margin-left: -100%;
        width: 70%;
        padding-bottom: 10%;
        margin-top: 20%;
    }

    .InformacionP article{        
        display: grid;
        grid-template-columns: repeat(2, 70%);
    }

    .InfoUno{
        grid-column: 2;
        grid-row: 1;        
        width: 180%;
    }

    .InfoDos{
        grid-column: 1;
        grid-row: 1;
        border-radius: 40%;
    }
</style>