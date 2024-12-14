<script>
import Tarjeta from "../Tarjetas/Tarje_Tas.vue";
import Lenguaje from "../Tarjetas/Ni_vel.vue";
import Precentacion from "../Tarjetas/Precen_tacion.vue";

export default {
    name: "VersionUno",
    components:{
        Tarjeta,
        Lenguaje,
        Precentacion
    },
    setup() {
        const Lenguage = "en";
        var título = String;
        //seguir con la traduccion
        if (Lenguage === "en") {
            título = "Projects";
        } else {
            título = "Proyectos"
        }
        return {Lenguage, título}
    }
}

</script>

<template>

    <body class="total">
        <div>
            <Lenguaje class="Lenguaje" :Lenguaje="Lenguage" />
        </div>
        <div>
            <Precentacion />
            <div>
                <h1>{{ título }}</h1>
                <Tarjeta v-model="idioma" />
            </div>

        </div>
    </body>
</template>
<style>
.total {
    display: grid;
    grid-template-columns: repeat(3, 30%);
}
</style>