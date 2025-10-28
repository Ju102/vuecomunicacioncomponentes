<template>
    <div style="margin: 20px;">
        <form>
            <label><b>Selecciona una o varias opciones:</b> </label>
            <multiselect id="multiselect" v-model="selected" :options="options" :multiple="true"></multiselect>
            <button v-on:click.prevent="mostrarDatos()">Mostrar</button>
        </form>
        <hr />
        <span v-if="mostrar == true">
            <div v-for="number in selected" :key="number">
                <p>{{ number }}</p>
            </div>
        </span>
    </div>
</template>

<script>

import Multiselect from 'vue-multiselect';

export default {
    name: "SeleccionMultiple",
    components: {
        Multiselect
    },
    data() {
        return {
            selected: [],
            options: ["Opcion 1", "Opción 2", "Opción 3", "Opción 4"],
            mostrar: false
        }
    },
    methods: {
        mostrarDatos() {
            this.mostrar = true;
        }
    }
}
</script>

<style src="vue-multiselect/dist/vue-multiselect.min.css" />

<style></style>