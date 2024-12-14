<script>
import { SobreMi } from "../Informacion/Páginas.js";
import { Datos } from "../Informacion/Dato.js";

export default {
    name: "PrecenTacion",

    props: {Lenguage: String},
    setup(props) {
        const Personal = SobreMi;
        const Informacion = Datos;
        const Leng = props.Lenguage;
        console.log(Leng);        
        return { Personal, Informacion, Leng }
    },
}

</script>

<template>
    <div v-for="D in Informacion" v-bind:key="D" class="InformacionP">
        <article v-for="SM in Personal" v-bind:key="SM">
            <div class="InfoUno">
                <div v-if="Leng = 'es'">
                    <h1>{{ SM.español.InicioUno }}</h1>
                    <h1>{{ SM.español.InicioDos }}</h1>
                    <h3>{{ SM.español.Detalle1a }} {{ SM.Detalle1b }}{{ SM.español.Detalle1c }}</h3>
                </div>
                <div v-else>                   
                    <h1>{{ SM.english.InicioUno }}</h1>
                    <h1>{{ SM.english.InicioDos }}</h1>
                    <h3>{{ SM.english.Detalle1a }} {{ SM.Detalle1b }}{{ SM.english.Detalle1c }}</h3>
                </div>
            </div>
            <img class="InfoDos" height="300px" width="260px" :src=D.Carpeta+SM.imagen1+D.ArchivoA />
        </article>
    </div>
</template>

<style>
.InformacionP {
    margin-left: -10%;
    width: 70%;
    padding-bottom: 10%;
    margin-top: 20%;
}

.InformacionP article {
    display: grid;
    grid-template-columns: repeat(2, 70%);
}

.InfoUno {
    grid-column: 2;
    grid-row: 1;
    width: 180%;
}

.InfoDos {
    grid-column: 1;
    grid-row: 1;
    border-radius: 40%;
}
</style>