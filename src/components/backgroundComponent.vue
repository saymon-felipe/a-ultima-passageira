<template>
    <div class="background"></div>
</template>
<script>
export default {
    name: "backgroundComponent"
}
</script>
<style scoped>
.background {
    background-image: url("../assets/img/fundo-ultima-passageira.jpg");
    background-position: center center;
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
    width: 100vw;
    height: 100vh;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    margin: auto;
    z-index: 1;
}
</style>