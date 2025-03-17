<template>
    <footer class="contrast">
        <p class="phrase fontsize-md">
            "A vida é feita de encontros e despedidas. Mas talvez, em algum lugar, a gente sempre se reencontre."
        </p>
        <div class="author">
            <p class="fontsize-md">Autor: Saymon F.</p>
            <a href="mailto:linnubr@gmail.com" class="fontsize-md" target="_blank">E-mail: linnubr@gmail.com</a>
        </div>
        <p class="signature fontsize-sm">&copy; {{ new Date().getFullYear() }} A Última Passageira - Todos os direitos reservados.</p>
    </footer>
</template>
<script>
export default {
    name: "footerComponent"
}
</script>
<style scoped>
footer {
    display: grid;
    place-items: center;
    padding: 6rem;
    gap: 6rem;
}
</style>