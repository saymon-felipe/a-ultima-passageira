<template>
    <section id="personagens">
        <div class="characters-container">
            <characterComponent v-for="(character, index) in characters" :character="character" :key="index" />
        </div>
    </section>
</template>
<script>
import characterComponent from "./characterComponent.vue";
import hiroshi from "../assets/img/illustration-hiroshi.png";
import miyo from "../assets/img/illustration-miyo.png";
import rina from "../assets/img/illustration-rina.png";

export default {
    name: "charactersComponent",
    data() {
        return {
            characters: [
                {
                    nameJapanese: "博",
                    namePortuguese: "Hiroshi",
                    description: '“Cresceu acreditando que o mundo era uma batalha a ser vencida. <br><br> Mas ao se aproximar de Miyo, Hiroshi descobre que há mais força em entender os outros do que em superá-los.“',
                    image: hiroshi,
                    principal: false
                },
                {
                    nameJapanese: "見よ",
                    namePortuguese: "Miyo",
                    description: '“Com um sorriso que esconde cicatrizes, Miyo enfrenta desafios diários sem perder a esperança. <br><br> Entre responsabilidades que não deveria carregar e sonhos incertos, ela segue em frente, aprendendo a confiar nos outros e em si mesma.“',
                    image: miyo,
                    principal: true
                },
                {
                    nameJapanese: "璃奈",
                    namePortuguese: "Rina",
                    description: '“Sempre pronta para rir ou brigar pelos amigos, Rina é o tipo de pessoa que transforma qualquer momento em algo memorável. <br><br> Por trás da energia vibrante, esconde um coração que sente tudo profundamente.“',
                    image: rina,
                    principal: false
                }
            ]
        }
    },
    components: {
        characterComponent
    }
}
</script>
<style scoped>
.characters-container {
    display: flex;
    align-items: center;
    justify-content: space-around;
    gap: var(--space-8);
    padding: 0 var(--space-5);
    overflow-x: auto;
    width: 100%;
}
</style>