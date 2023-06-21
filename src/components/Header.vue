<template>
  <header class="header container">
    <div class="header__wrapper-menu-open">
      <div
        :class="[this.menuIsOpen ? 'header__menu_open' : 'header__menu']"
        v-on:click="clickMenu"
      ></div>
      <div>
        <img class="header__logo" alt="Bank logo" src="../assets/logo.svg" />
      </div>
    </div>
    <div :class="[!this.menuIsOpen ? 'menu_hidden' : '', 'menu']">
      <ul class="menu__list">
        <li>
          <a href="#" class="menu__list-item" target="_blank"
            >Какие преимущества</a
          >
        </li>
        <li>
          <a href="#" class="menu__list-item" target="_blank"
            >Что вы получаете</a
          >
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
  </header>
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

  .header__wrapper-menu-open {
    position: relative;
    display: flex;
    align-items: center;

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
}

.menu {
  @extend %reset-default-styles;
  max-width: 393px;
  position: absolute;
  background: #1c1c1b;
  top: 0;
  left: 0;
  padding: 93px 99px 100%;
  transition: left 0.4s ease-out;
  height: 100%;

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

@media (max-width: 1900px) {
  .menu {
    padding-right: 60px;
    padding-left: 60px;
  }
}

@media (max-width: 1680px) {
  .header {
    padding-top: 50px;
    padding-right: 10px;
    padding-left: 10px;

    .menu {
      padding: 0;
      position: initial;
      background: none;
      width: 100%;
      max-width: 100%;
      height: auto;

      .menu__list {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
      }

      .menu__contact {
        margin-top: 10px;
        flex-direction: row;
        justify-content: flex-end;
        column-gap: 30px;

        .menu__contact-number {
          font-size: 20px;
        }
      }
    }
    .header__menu {
      display: none;
    }
    .header__menu_open {
      display: none;
    }
    .header__logo {
      width: 90%;
    }
  }
}
@media (max-width: 980px) {
  .header__wrapper-menu-open {
    max-width: 170px;
  }
  .menu .menu__list .menu__list-item {
    font-size: 13px;
    font-weight: $weight-medium;
  }
  .header .menu .menu__contact .menu__contact-number {
    font-size: 15px;
  }
}

@media (max-width: 680px) {
  .header .header__logo {
    width: 100%;
  }
  .header .menu .menu__list {
    display: none;
  }
}

@media (max-width: 480px) {
  .header {
    flex-direction: row;
    flex-wrap: wrap;
  }
}
</style>
