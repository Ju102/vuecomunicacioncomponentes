<template>
    <div style="padding: 20px;">
        <h2>Ejemplo de Checkbox</h2>
        <button @click="generarNumero()">Generar Checkbox</button><br /><br /><br />
        <span v-for="(numero, index) in numeros" :key="'numero-' + index" style="margin-left: 10px;">
            <!-- bind the index as the checkbox value so repeated numbers don't share the same value -->
            <input type="checkbox" :value="index" v-model="sumandos" />
            <label>{{ numero }}</label>
        </span>
        <hr />
        <p>Suma total: {{ suma }}</p>
    </div>
</template>

<script>
export default {
    name: "SumaCheckbox",
    data() {
        return {
            numeros: [],
            sumandos: []
        }
    },
    methods: {
        generarNumero() {
            var rand = parseInt(Math.random() * 100) + 1;
            this.numeros.push(rand);
        },
    },
    computed: {
        // suma los números a partir de los índices seleccionados
        suma() {
            if (this.sumandos.length === 0) return 0;
            return this.sumandos.reduce((suma, numero) => {
                const i = parseInt(numero);
                if (Number.isNaN(i) || i < 0 || i >= this.numeros.length) return suma;
                return suma + (this.numeros[i] || 0);
            }, 0);
        }
    }
}
</script>

<style></style>