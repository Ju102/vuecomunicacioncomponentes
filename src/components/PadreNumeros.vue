<template>
    <div style="padding: 10px; border-radius: 7px; border: 1px solid black">
        <h1>Números Padre</h1>
        <h3 style="color: red">Suma total: {{ suma }}</h3>
        <button @click="generarNumeroAleatorio()">Random</button>
        <hr v-if="numeros.length != 0"/>
        <span v-for="num in numeros" :key="num">
            <HijoNumero :num="num" v-on:sumar="sumar" />
        </span>
    </div>
</template>

<script>

import HijoNumero from './HijoNumero.vue';

export default {
    name: "PadreNumeros",
    components: { HijoNumero},
    data() {
        return {
            numeros: [],
            suma: 0
        }
    },
    methods: {
        generarNumeroAleatorio() {
            var nuevo = parseInt(Math.random() * 100) + 1;

            this.numeros.push(nuevo);
        },
        sumar(numero) {
            this.suma += numero;
        }
    }
}
</script>

<style></style>