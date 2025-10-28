<template>
    <div style="border: 1px solid black; margin: 10px; padding: 5px">
        <h3 style="color: darkcyan">Deporte: {{ nombredeporte }} (Child)</h3> <button style="background-color:firebrick; padding: 5px;
        border-radius: 5px; color: whitesmoke; font-weight: bold;" @click="seleccionarFavorito()">FAV</button>
    </div>
</template>

<script>
export default {
    name: "HijoDeporte",
    props: ["nombredeporte"],
    mounted() {
        console.log(this.nombredeporte);
    },
    methods: {
        seleccionarFavorito() {
            console.log("Soy el hijo: " + this.nombredeporte);
            this.$emit("seleccionarFavoritoParent", this.nombredeporte);
        }
    }
}
</script>

<style></style>