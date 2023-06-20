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
html,
body {
  margin: 0;
}

#app {
  font-family: Geometria, Arial, sans-serif;
  margin: 0 auto;
  box-sizing: border-box;
  padding: 0;
  color: #fff;
  position: relative;
  background-color: #0e0e0e;
}
.container {
  max-width: 980px;
  margin: 0 auto;
  position: relative;
}
</style>
