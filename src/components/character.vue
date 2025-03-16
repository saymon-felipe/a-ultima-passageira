<template>
    <div class="character" :class="character.principal ? 'principal' : ''">
        <img :src="character.image" :alt="character.portugueseName">
        <div class="name">
            <p class="japanese-name">{{ character.japaneseName }}</p>
            <p class="portuguese-name">{{ character.portugueseName }}</p>
        </div>
        <p class="description" v-html="character.description"></p>
    </div>
</template>
<script>
export default {
    name: "character",
    props: "character"
}
</script>