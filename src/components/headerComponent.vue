<template>
    <header>
        <ul>
        <li>
            <a href="#inicio">
                Início
            </a>
        </li>
        <li>
            <a href="#sobre">
                Sobre
            </a>
        </li>
        <li>
            <a href="#personagens">
                Personagens
            </a>
        </li>
        <li>
            <a href="#previa">
                Prévia
            </a>
        </li>
        <li>
            <a href="#comprar">
                Comprar
            </a>
        </li>
        </ul>
    </header>
</template>
<script>
export default {
    name: "headerComponent"
}
</script>
<style scoped>
header {
    background: var(--background-black-opacity);
    backdrop-filter: blur(var(--blur));
    width: 100%;
    padding: var(--space-5);
    display: grid;
    place-items: center;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 10;

    & ul {
        list-style: none;
        padding: 0;
        margin: 0;
        display: flex;
        align-items: center;

        & li {
            margin: 0 var(--space-5);
            cursor: pointer;
            transition: color 0.4s ease-in-out;
            color: var(--white);

            &:hover {
                color: var(--blue);
            }
        }
    }
}
</style>