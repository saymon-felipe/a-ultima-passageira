<template>
    <footer>
        <p class="phrase">
            "A vida é feita de encontros e despedidas. Mas talvez, em algum lugar, a gente sempre se reencontre."
        </p>
        <div class="author">
            <p>Autor: Saymon F.</p>
            <a href="mailto:linnubr@gmail.com" target="_blank">E-mail: linnubr@gmail.com</a>
        </div>
        <p class="signature">&copy; {{ new Date().getFullYear() }} A Última Passageira - Todos os direitos reservados.</p>
    </footer>
</template>
<script>
export default {
    name: "footerComponent"
}
</script>