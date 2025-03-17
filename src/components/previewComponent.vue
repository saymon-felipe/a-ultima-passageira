<template>
    <section id="previa">
        <PDF src="/pdf/a-ultima-passageira-preview.pdf" />
    </section>
</template>
<script>
import PDF from "pdf-vue3";

export default {
    components: {
        PDF
    }
}
</script>
<style>
.pdf-vue3-canvas-container {
    margin: 0px auto;
    width: 100%;
    display: flex;
    overflow-x: auto;
    overflow-y: hidden;
    height: 100%;

    & canvas {
        height: calc(100vh - 200px) !important;
    }
}
</style>
  