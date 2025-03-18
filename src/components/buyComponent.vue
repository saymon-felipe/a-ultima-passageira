<template>
    <section class="contrast" id="comprar">
        <div class="buy">
            <img src="../assets/img/book-mockup.png" alt="Livro A Última Passageira">
            <div class="book-informations">
                <div class="book-name">
                    <p class="fontsize-lg">最後の乗客</p>
                    <p class="fontsize-md">(A Última Passageira)</p>
                </div>
                <div class="book-footer">
                    <p>
                        Inspirado em uma história real que emocionou o mundo, A Última Passageira acompanha a jornada de Miyo Sato, uma jovem marcada por perdas e escolhas difíceis.
                        <br><br>
                        Após um acontecimento que muda sua vida para sempre, Miyo recebe uma segunda chance — não apenas para corrigir os erros do passado, mas para reencontrar aqueles que ama e redescobrir o verdadeiro significado de seguir em frente.
                        <br><br>
                        Entre despedidas e reencontros, amor e redenção, esta é uma história sobre o tempo, os laços que nos definem e as estações que deixamos para trás.
                    </p>
                </div>
                <a href="" target="_blank" class="btn primary">Comprar</a>
            </div>
        </div>
    </section>
</template>
<script>
export default {
    name: "buyComponent"
}
</script>
<style scoped>
.buy {
    display: grid;
    place-items: center;
    gap: var(--space-12);
    grid-template-columns: 1fr 2fr;

    & img {
        width: 100%;
    }
}

.book-informations {
    display: grid;
    gap: var(--space-8);
}

@media (max-width: 768px) {
    .buy {
        grid-template-columns: 1fr;
        text-align: center;

        & img {
            height: 200px;
            width: initial;
        }
    }

    .book-footer p {
        font-size: 15px;
    }

    a {
        margin: auto;
    }
}
</style>