<template>
    <div>
        <h3 style="color: darkcyan">Deporte: {{ nombredeporte }} (Child)</h3>
    </div>
</template>

<script>
export default {
    name: "HijoDeporte",
    props: ["nombredeporte"]
}
</script>

<style></style>