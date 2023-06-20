<template>
  <header>
    <div class="header container">
      <div
        :class="[this.menuIsOpen ? 'header__menu_open' : 'header__menu']"
        v-on:click="clickMenu"
      ></div>
      <div class="header__logo">
        <img alt="Bank logo" src="../assets/logo.svg" />
      </div>
    </div>
  </header>
  <div :class="[!this.menuIsOpen ? 'menu_hidden' : '', 'menu']">
    <ul class="menu__list">
      <li>
        <a href="#" class="menu__list-item" target="_blank"
          >Какие преимущества</a
        >
      </li>
      <li>
        <a href="#" class="menu__list-item" target="_blank">Что вы получаете</a>
      </li>
      <li>
        <a href="#" class="menu__list-item" target="_blank">Еще сюрпризы</a>
      </li>
      <li>
        <button type="button" class="menu__list-item" v-on:click="openPopup">
          Оформить карту
        </button>
      </li>
    </ul>
    <ul class="menu__contact">
      <li class="menu__contact-item">
        <span>По России</span>
        <a href="”tel:+78009506570" class="menu__contact-number"
          >8 800 950 6570</a
        >
      </li>
      <li class="menu__contact-item">
        <span>По Миру</span>
        <a href="”tel:+78009506570" class="menu__contact-number"
          >8 800 950 6570</a
        >
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Header",

  props: {
    popupIsOpen: {
      type: Boolean,
    },
    menuIsOpen: {
      type: Boolean,
    },
  },
  emits: ["clickMenu", "openPopup"],

  methods: {
    clickMenu() {
      this.$emit("clickMenu");
    },
    openPopup() {
      this.$emit("openPopup");
    },
  },
};
</script>

<style lang='scss' scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.header {
  @extend %reset-default-styles;
  display: flex;
  align-items: center;
  padding-top: 86px;

  .header__menu {
    background-image: url("../assets/menu.svg");
    background-repeat: no-repeat;
    width: 25px;
    height: 19px;
    position: absolute;
    left: -73px;
  }

  .header__menu:hover,
  .header__menu_open:hover {
    cursor: $cursor-hover;
  }

  .header__menu_open {
    background-image: url("../assets/menu-open.svg");
    background-repeat: no-repeat;
    width: 65px;
    height: 60px;
    position: absolute;
    left: -93px;
  }
}

.menu {
  @extend %reset-default-styles;
  max-width: 393px;
  position: absolute;
  background: #1c1c1b;
  top: 0;
  left: 0;
  padding: 93px 99px 100%;
  height: 100%;
  transition: left 0.4s ease-out;

  .menu__list {
    @extend %reset-default-styles;
    list-style: none;
    display: flex;
    flex-direction: column;
    row-gap: 25px;

    .menu__list-item {
      @extend %reset-default-styles;
      text-decoration: none;
      font-weight: $weight-bold;
      font-size: 18px;
      line-height: 1.667;
      color: #fff;
      background: none;
      border: none;
    }

    .menu__list-item:hover {
      cursor: $cursor-hover;
    }
  }
  .menu__contact {
    @extend %reset-default-styles;
    margin-top: 508px;
    display: flex;
    flex-direction: column;
    row-gap: 12px;
    list-style: none;

    .menu__contact-item {
      display: flex;
      color: #6c6c6c;
      flex-direction: column;
      row-gap: 4px;

      .menu__contact-number {
        color: #bbbbbb;
        font-size: 24px;
        line-height: 1.5;
        text-decoration: none;
      }
    }
  }
}

.menu_hidden {
  left: -100%;
  transition: left 0.5s ease-in 0.1s;
}
</style>
