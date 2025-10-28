<template>
    <div>
        <h1>Comics Parent</h1>
        <form v-on:submit.prevent="createComic()">
            <label>Título: </label>
            <input type="text" v-model="comicForm.titulo" />
            <label>Imagen: </label>
            <input type="text" v-model="comicForm.imagen" />
            <label>Descripción: </label>
            <input type="text" v-model="comicForm.descripcion" />
            <label>Año: </label>
            <input type="number" v-model="comicForm.year" />
            <button>Añadir</button>
        </form>
        <div v-if="favorito != null" style="margin: 40px">
            <img :src="favorito.imagen" />
            <h3>{{ favorito.titulo }}</h3>
            <p>{{ favorito.descripcion }}</p>
            <p :class="{
                rojo: favorito.year < 2000,
                verde: favorito.year >= 2000
            }">Año de salida: {{ favorito.year }}</p>
        </div>
        <hr>
        <div style="background-color: red;">
            <div id="comics" v-for="(comic, index) in comics" :key="comic">
                <ComicComponent :comic="comic" :index="index" v-on:seleccionarFav="seleccionarFavorito"
                    v-on:deleteComic="deleteComic" />
            </div>
        </div>
    </div>
</template>

<script>

import ComicComponent from './ComicComponent.vue';

export default {
    name: "ComicsComponent",
    components: {
        ComicComponent
    },
    data() {
        return {
            comicForm: {
                titulo: "",
                imagen: "",
                descripcion: "",
                year: 0
            },
            favorito: null,
            comics: [
                {
                    titulo: "Spiderman",
                    imagen:
                        "https://3.bp.blogspot.com/-i70Zu_LAHwI/T290xxduu-I/AAAAAAAALq8/8bXDrdvW50o/s1600/spiderman1.jpg",
                    descripcion: "Hombre araña",
                    year: 1997
                },
                {
                    titulo: "Wolverine",
                    imagen:
                        "https://images-na.ssl-images-amazon.com/images/I/51c1Q1IdUBL._SX259_BO1,204,203,200_.jpg",
                    descripcion: "Lobezno",
                    year: 2003
                },
                {
                    titulo: "Guardianes de la Galaxia",
                    imagen:
                        "https://www.tebeosfera.com/T3content/img/T3_muestras/T3_numeros/3/4/m_guardianes_de_la_galaxia_2017_panini_-guardianes_del_infinito-_861934.jpg",
                    descripcion: "Yo soy Groot",
                    year: 2006
                },
                {
                    titulo: "Avengers",
                    imagen:
                        "https://d26lpennugtm8s.cloudfront.net/stores/057/977/products/ma_avengers_01_01-891178138c020318f315132687055371-640-0.jpg",
                    descripcion: "Los Vengadores",
                    year: 1993
                },
                {
                    titulo: "Spawn",
                    imagen:
                        "https://i.pinimg.com/originals/e1/d8/ff/e1d8ff4aeab5e567798635008fe98ee1.png",
                    descripcion: "Al Simmons",
                    year: 2000
                },
                {
                    titulo: "Batman",
                    imagen:
                        "https://www.comicverso.com/wp-content/uploads/2020/06/The-Killing-Joke-657x1024.jpg",
                    descripcion: "Murcielago",
                    year: 2001
                }
            ]

        }
    },
    methods: {
        seleccionarFavorito(comic) {
            this.favorito = comic;
        },
        createComic() {
            this.comics.push(this.comicForm);
        },
        deleteComic(ind) {
            this.comics.splice(ind, 1);
        }
    }
}
</script>

<style>
@import './../assets/css/comics.css';
</style>