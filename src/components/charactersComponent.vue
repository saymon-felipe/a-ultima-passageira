<template>
    <section>
        <div class="characters-container">
            <character v-for="(character, index) in characters" :character="character" :key="index" />
        </div>
    </section>
</template>
<script>
import character from "./character.vue";

export default {
    name: "charactersComponent",
    data() {
        return {
            characters: [
                {
                    nameJapanese: "博",
                    namePortuguese: "Hiroshi",
                    description: '“Cresceu acreditando que o mundo era uma batalha a ser vencida. <br> Mas ao se aproximar de Miyo, Hiroshi descobre que há mais força em entender os outros do que em superá-los.“',
                    image: require("../assets/img/illustration-hiroshi.png"),
                    principal: false
                },
                {
                    nameJapanese: "見よ",
                    namePortuguese: "Miyo",
                    description: '“Com um sorriso que esconde cicatrizes, Miyo enfrenta desafios diários sem perder a esperança. <br> Entre responsabilidades que não deveria carregar e sonhos incertos, ela segue em frente, aprendendo a confiar nos outros e em si mesma.“',
                    image: require("../assets/img/illustration-miyo.png"),
                    principal: true
                },
                {
                    nameJapanese: "璃奈",
                    namePortuguese: "Rina",
                    description: '“Sempre pronta para rir ou brigar pelos amigos, Rina é o tipo de pessoa que transforma qualquer momento em algo memorável. <br> Por trás da energia vibrante, esconde um coração que sente tudo profundamente.“',
                    image: require("../assets/img/illustration-rina.png"),
                    principal: false
                }
            ]
        }
    },
    components: {
        character
    }
}
</script>