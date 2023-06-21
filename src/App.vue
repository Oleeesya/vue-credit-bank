<template>
  <Main />
</template>

<script>
import Main from "./components/Main.vue";
import ".//vendor/fonts/fonts.css";

export default {
  name: "App",
  components: {
    Main,
  },
};
</script>

<style lang='scss'>
@import "./assets/variables.scss";
@import "./assets/extends.scss";

#app {
  @extend %reset-default-styles;
  font-family: Geometria, Arial, sans-serif;
  color: #fff;
  position: relative;
  background-color: #0e0e0e;
}
.container {
  max-width: 980px;
  margin: 0 auto;
}

@media (max-width: 980px) {
  .container {
    max-width: 680px;
    padding-right: 10px;
    padding-left: 10px;
  }
}

@media (max-width: 680px) {
  .container {
    max-width: 480px;
  }
}

@media (max-width: 480px) {
  .container {
    max-width: 320px;
  }
}
</style>
