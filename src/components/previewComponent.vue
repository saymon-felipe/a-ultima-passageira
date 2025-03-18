<template>
    <section id="previa">
        <button v-on:click="prevSlide()">
            <i class="fa-solid fa-angle-left"></i>
        </button>
        <PDF src="/pdf/a-ultima-passageira-preview.pdf" />
        <button v-on:click="nextSlide()">
            <i class="fa-solid fa-angle-right"></i>
        </button>
        <div class="responsive-buttons">
            <button v-on:click="prevSlide()">
                <i class="fa-solid fa-angle-left"></i>
            </button>
            <button v-on:click="nextSlide()">
                <i class="fa-solid fa-angle-right"></i>
            </button>
        </div>
    </section>
</template>
<script>
import PDF from "pdf-vue3";
import $ from 'jquery';

export default {
    components: {
        PDF
    },
    data() {
        return {
            prev: 0,
            next: 0
        }
    },
    methods: {
        prevSlide: function () {
            const canvaWidth = document.querySelector(".pdf-vue3-canvas-container canvas").offsetWidth;
            const scroller = document.querySelector(".pdf-vue3-canvas-container");

            if (scroller.scrollLeft > 0) {
                this.prev++;

                this.saveCurrentPage();
            }

            scroller.scrollTo({ left: scroller.scrollLeft - canvaWidth, behavior: "smooth" });
        },
        nextSlide: function () {
            const canvaWidth = document.querySelector(".pdf-vue3-canvas-container canvas").offsetWidth;
            const scroller = document.querySelector(".pdf-vue3-canvas-container");
            
            if (scroller.scrollLeft + scroller.clientWidth < scroller.scrollWidth) {
                this.next++;

                this.saveCurrentPage();
            }

            scroller.scrollTo({ left: scroller.scrollLeft + canvaWidth, behavior: "smooth" });
        },
        saveCurrentPage: function () {
            let steps = this.next - this.prev;

            let scrollTarget = steps * (document.querySelector(".pdf-vue3-canvas-container canvas").offsetWidth);

            localStorage.setItem("currentScroll", scrollTarget);
        }
    },
    mounted: function () {
        let interval = setInterval(() => {
            if ($(".pdf-vue3-canvas-container canvas").is(":visible")) {
                if (localStorage.getItem("currentScroll")) {
                    document.querySelector(".pdf-vue3-canvas-container").scrollLeft = localStorage.getItem("currentScroll");
                }
                clearInterval(interval);
            }
        }, 1000)
        
    }
}
</script>
<style>
.responsive-buttons {
    display: none;
    align-items: center;
    gap: var(--space-5);
}

#previa {
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: var(--space-5);

    & button {
        width: 40px;
        height: 40px;
        min-width: 40px;
        min-height: 40px;
        max-width: 40px;
        max-height: 40px;
        border-radius: 50%;
        display: grid;
        place-items: center;
        background: var(--blue);
        color: var(--purple);
        border: none;
        cursor: pointer;

        &:hover {
            background: var(--blue-low);
        }
    }
}

.pdf-vue3-scroller {
    display: grid;
    place-items: center;
    overflow: hidden !important;
}

.pdf-vue3-canvas-container {
    margin: 0px auto;
    width: 100%;
    display: flex;
    overflow: hidden;
    height: fit-content;
    scroll-snap-type: x mandatory;
    height: 100%;

    & canvas {
        scroll-snap-align: start;
        width: 50% !important;
        min-width: 50% !important;
        max-width: 50% !important;
        height: 100% !important;
        object-fit: contain;
        overflow: hidden;
        box-shadow: none !important;
    }
}

@media (max-width: 768px) {
    .pdf-vue3-canvas-container canvas {
        width: 100% !important;
        min-width: 100% !important;
        max-width: 100% !important;
    }

    #previa > button {
        display: none;
    }

    #previa {
        display: grid;
        place-items: center;
    }

    #previa .responsive-buttons {
        display: flex;
    }
}
</style>
  