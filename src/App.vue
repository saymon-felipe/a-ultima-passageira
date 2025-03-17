<template>
  <headerComponent />
  <homeComponent />

  <playerComponent />

  <aboutComponent />
  <charactersComponent />
  <previewComponent />
  <buyComponent />
  <footerComponent />
  <backgroundComponent />
</template>
<script>
import homeComponent from "./components/homeComponent.vue";
import headerComponent from "./components/headerComponent.vue";
import aboutComponent from "./components/aboutComponent.vue";
import charactersComponent from "./components/charactersComponent.vue";
import previewComponent from "./components/previewComponent.vue";
import buyComponent from "./components/buyComponent.vue";
import footerComponent from "./components/footerComponent.vue";
import playerComponent from "./components/playerComponent.vue";
import backgroundComponent from "./components/backgroundComponent.vue";

export default {
  components: {
    homeComponent,
    headerComponent,
    aboutComponent,
    charactersComponent,
    previewComponent,
    buyComponent,
    footerComponent,
    playerComponent,
    backgroundComponent
  }
}
</script>
