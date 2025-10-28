<template>
    <div>
        <h1 style="color: firebrick">Lista de Deportes (Parent)</h1>

        <div v-if="favorito != null">
            <p>Deporte favorito: {{ favorito }}</p>
            <hr />
        </div>

        <span v-for="deporte in deportes" :key="deporte">
            <HijoDeporte :nombredeporte="deporte" v-on:seleccionarFavoritoParent="seleccionarFavorito"/>
        </span>
    </div>
</template>

<script>

import HijoDeporte from './HijoDeporte.vue'

export default {
    name: "PadreDeportes",
    components: { HijoDeporte },
    data() {
        return {
            deportes: ["Fútbol", "Baloncesto", "Tenis", "Rugby"],
            favorito: null
        }
    }, methods: {
        seleccionarFavorito(deporteFav) {
            console.log("Yo soy el Parent");
            this.favorito = deporteFav;
        }
    }


}
</script>

<style></style>