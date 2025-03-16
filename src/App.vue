<template>
  <headerComponent />
  <homeComponent />

  <playerComponent />

  <aboutComponent />
  <previewComponent />
  <buyComponent />
  <footerComponent />
</template>
<script>
import homeComponent from "./components/homeComponent.vue";
import headerComponent from "./components/headerComponent.vue";
import aboutComponent from "./components/aboutComponent.vue";
import previewComponent from "./components/previewComponent.vue";
import buyComponent from "./components/buyComponent.vue";
import footerComponent from "./components/footerComponent.vue";
import playerComponent from "./components/playerComponent.vue";

export default {
  components: {
    homeComponent,
    headerComponent,
    aboutComponent,
    previewComponent,
    buyComponent,
    footerComponent,
    playerComponent
  }
}
</script>
