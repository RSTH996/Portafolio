<script setup>
import { Datos } from "../Informacion/Dato.js";
import { Creaciones } from "../Informacion/Páginas.js";
</script>

<template>
    <div>
        <div class="Projectos" v-for=" I in Creaciones" :key="I.ID">
            <article v-for="D in Datos" v-bind:key="D.D">
                <h2>{{ I.Nombre }}</h2>
                <h3>{{ I.Detalle }}</h3>
                <p>{{ I.Informacion }}</p>
                <p>{{ I.Framework }}</p>
                <div>
                    <img height="400px" width="550px" :src=D.Carpeta+I.imgen+D.ArchivoA />
                    <a v-bind:href="I.Reedireccion"><button>Ver la projecto en: {{ I.Reedireccion }}</button></a>
                </div>
            </article>
        </div>
    </div>
</template>

<style>
.Projectos {    
    visibility: visible;
    display: flex;
    text-align: center;
    grid-column: 2;
    background-color: rgb(231, 231, 231);
    width: 120%;
    margin-left: -100%;
}

.Projectos img {
    padding-bottom: 3%;
}

.Projectos a {
    text-decoration: none;
    color: rgb(0, 0, 0);
}

.Projectos button {
    width: 100%;
    height: 50px;
    background-color: rgb(228, 225, 78);
    border-color: rgb(228, 225, 78);
}
</style>