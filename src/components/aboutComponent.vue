<template>
    <section class="contrast" id="sobre">
        <div class="left">
            <h1>
                忍 <br> 耐
            </h1>
            <p>(perseverança)</p>
        </div>
        <div class="right">
            <p class="fontsize-md">Em uma pequena estação de trem esquecida pelo tempo, Miyo Sato embarca em uma jornada que mudará sua vida para sempre. Entre a neve silenciosa de Hokkaido e os desafios de sua juventude, ela enfrenta a pressão da escola, a doença da mãe e o peso das responsabilidades que não deveria carregar sozinha.</p>
            <br>
            <p class="fontsize-sm">Quando um inesperado ato de coragem surge em meio à rivalidade, Miyo descobre que até mesmo aqueles que parecem inalcançáveis podem esconder cicatrizes invisíveis. Em um cenário onde despedidas são inevitáveis, o que realmente significa seguir em frente?</p>
            <br>
            <strong>
                <p class="fontsize-sm">Uma história sobre laços, perdas e a força invisível que nos impulsiona a continuar, mesmo quando tudo parece perdido.</p>
            </strong>
        </div>
    </section>
</template>
<script>
export default {
    name: "aboutComponent"
}
</script>
<style scoped>
#sobre {
    grid-template-columns: 1fr 3fr;
    gap: var(--space-8);
}

.left {
    display: grid;
    place-items: center;
    gap: var(--space-5);

    h1 {
        font-size: 8rem;
    }
}
</style>