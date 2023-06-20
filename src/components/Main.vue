<template>
  <div :class="[menuIsOpen ? 'main_menu_open' : 'main_menu_close', 'main']">
    <Header
      @openPopup="openPopup"
      :popupIsOpen="popupIsOpen"
      :menuIsOpen="menuIsOpen"
      @clickMenu="clickMenu"
    />
    <AboutCard @openPopup="openPopup" :popupIsOpen="popupIsOpen" />
    <PackagePrivilege />
    <Bonus />
    <Assistant />
    <Release @openPopup="openPopup" :popupIsOpen="popupIsOpen" />
    <Footer />
    <PopupWithForm @closePopup="closePopup" :popupIsOpen="popupIsOpen" />
  </div>
</template>

<script>
import Header from "./Header.vue";
import AboutCard from "./AboutCard.vue";
import PackagePrivilege from "./PackagePrivilege.vue";
import Bonus from "./Bonus";
import Assistant from "./Assistant";
import Release from "./Release";
import Footer from "./Footer";
import PopupWithForm from "./PopupWithForm";

export default {
  name: "Main",
  components: {
    Header,
    AboutCard,
    PackagePrivilege,
    Bonus,
    Assistant,
    Release,
    Footer,
    PopupWithForm,
  },
  data() {
    return {
      popupIsOpen: false,
      menuIsOpen: false,
    };
  },

  methods: {
    openPopup() {
      this.popupIsOpen = true;
    },
    closePopup() {
      this.popupIsOpen = false;
    },
    clickMenu() {
      this.menuIsOpen = !this.menuIsOpen;
    },
  },
};
</script>

<style lang='scss'>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.main {
  @extend %reset-default-styles;
  margin: 0;
}
.main_menu_open {
  margin-left: 76px;
  transition: margin-left 0.25s linear 0.18s;
}
.main_menu_close {
  margin-left: 0;
  transition: margin-left 0.3s linear;
}
</style>