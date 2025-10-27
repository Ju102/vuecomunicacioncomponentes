<template>
    <div>
        <h1 style="color: firebrick">Lista de Deportes (Parent)</h1>
        <span v-for="deporte in deportes" :key="deporte">
            <HijoDeporte :nombredeporte="deporte"/>
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
            deportes: ["Fútbol", "Baloncesto", "Tenis", "Rugby"]
        }
    }


}
</script>

<style></style>