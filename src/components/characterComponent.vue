<template>
    <div class="character" :class="character.principal ? 'principal' : ''">
        <img :src="character.image" :alt="character.namePortuguese">
        <div class="name">
            <p class="japanese-name fontsize-md">{{ character.nameJapanese }}</p>
            <p class="portuguese-name fontsize-md">{{ character.namePortuguese }}</p>
        </div>
        <p class="description" v-html="character.description"></p>
    </div>
</template>
<script>
export default {
    name: "characterComponent",
    props: ["character"]
}
</script>
<style scoped>
.character {
    background: var(--background-black-opacity);
    padding: var(--space-8);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: var(--space-5);
    width: 248px;
    min-width: 248px;
    max-width: 248px;
    min-height: 608px;
    text-align: center;

    & img {
        width: 100%;
    }
}

.principal {
    box-shadow: 0 0 8px 3px var(--blue);
}
</style>