<template>
    <div style="margin: 40px">
        <img :src="comic.imagen" />
        <h3>{{ comic.titulo }}</h3>
        <p>{{ comic.descripcion }}</p>
        <p :class="{
            rojo: comic.year < 2000,
            verde: comic.year >= 2000
        }">Año de salida: {{ comic.year }}</p>
        <button @click="selectFavorito()">FAV</button>
        <button @click="deleteComic()">Eliminar</button>
    </div>
</template>

<script>
export default {
    name: "ComicComponent",
    props: ["comic", "index"],
    methods: {
        selectFavorito() {
            this.$emit("seleccionarFav", this.comic);
        },
        deleteComic() {
            this.$emit("deleteComic", this.index);
        }
    }
}
</script>

<style>
@import './../assets/css/comics.css';
</style>