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
.pdf-vue3-scroller {
    display: grid;
    place-items: center;
}

.pdf-vue3-canvas-container {
    margin: 0px auto;
    width: 100%;
    display: flex;
    overflow-x: auto;
    overflow-y: hidden;
    height: fit-content;
    scroll-snap-type: x mandatory;

    & canvas {
        scroll-snap-align: start;
        width: 50% !important;
        min-width: 50% !important;
        max-width: 50% !important;
        aspect-ratio: 9/16 !important;
        height: initial !important;
        border-radius: 1rem;
        overflow: hidden;
    }
}

@media (max-width: 768px) {
    .pdf-vue3-canvas-container canvas {
        width: 100% !important;
        min-width: 100% !important;
        max-width: 100% !important;
    }
}
</style>
  