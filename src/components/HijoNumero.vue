<template>
    <div style="border: 1px solid black; margin: 10px; padding: 5px; background-color: cadetblue;
    border-radius: 7px;">
        <h3 style="color: blue">Número Hijo: {{ num }}</h3>
        <button @click="enviarNumero()">Sumar</button>
    </div>
</template>

<script>
export default {
    name: "HijoNumero",
    props: ["num"],
    mounted() {
        console.log("Component Child " + this.num + " montado");
    },
    methods: {
        enviarNumero() {
            this.$emit("sumar",this.num);
        }
    }
}
</script>

<style></style>