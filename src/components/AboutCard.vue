<template>
  <div class="about-card">
    <div class="container">
      <h1 class="about-card__title">
        Твоя премиум карта
        <span class="about-card__title_description">
          Лучшая карта для любителей путешествий
        </span>
      </h1>

      <ul class="about-card__list">
        <div class="about-card__list-item">
          <li>
            <span class="about-card__percent">11%</span>
            <p class="about-card__description">
              Вернем <br />
              за покупки милями
            </p>
          </li>
          <li>
            <span class="about-card__percent">7%</span>
            <p class="about-card__description">
              До 7% <br />
              на остаток <br />
              по счету
            </p>
          </li>
        </div>
        <div class="about-card__list-item">
          <li>
            <span class="about-card__percent">0%</span>
            <p class="about-card__description">
              Бесплатное снятие наличных по всему миру
            </p>
          </li>
          <li>
            <span class="about-card__percent">0р</span>
            <p class="about-card__description">
              Бесплатное годовое обслуживание
            </p>
          </li>
        </div>
      </ul>

      <button type="button" class="btn" v-on:click="this.openPopup">
        Заказать сейчас
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutCard",

  props: {
    popupIsOpen: {
      type: Boolean,
    },
  },

  methods: {
    openPopup() {
      this.$emit("openPopup");
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.about-card {
  @extend %reset-default-styles;
  margin-top: 100px;
  padding-bottom: 278px;
  background: url("../assets/credit-card.svg") 100% 0 no-repeat,
    url("../assets/bg-line.svg") -335px 0 repeat-x;

  .container {
    .about-card__title {
      margin: 0;
      max-width: 735px;
      line-height: 0.964;
      font-size: 96px;
      font-weight: $weight-heavy;

      .about-card__title_description {
        font-size: 23px;
        line-height: 1;
        color: #6c6c6c;
        max-width: 303px;
        display: $span-img-or-description;
        font-weight: $weight-extra-bold;
      }
    }

    .about-card__list {
      @extend %reset-default-styles;
      margin-top: 84px;
      margin-left: 0;
      list-style-type: none;
      font-weight: $weight-bold;
      max-width: 279.19px;
      display: flex;
      column-gap: 42.19px;

      .about-card__list-item {
        display: flex;
        flex-direction: column;
        row-gap: 36px;
        min-width: 110px;
      }

      .about-card__percent {
        margin: 0;
        padding: 0;
        color: #c0965c;
        font-size: 36px;
        line-height: 1;
      }

      .about-card__description {
        margin: 0;
        padding: 0;
        color: #6c6c6c;
        font-size: 14px;
        line-height: 1.43;
      }
    }

    .btn {
      @extend %reset-default-styles;
      margin-top: 69px;
      background-color: #c0965c;
      color: #fff;
      font-size: 24px;
      font-weight: $weight-bold;
      border: none;
      border-radius: 10px;
      width: 290px;
      height: 80px;
    }

    .btn:hover {
      cursor: $cursor-hover;
    }
  }
}

@media (max-width: 1480px) {
  .about-card {
    background-size: 60%, auto;
    background-position-y: 20%;
  }
}
@media (max-width: 980px) {
  .about-card {
    padding-bottom: 89px;

    .container .about-card__title {
      font-size: 60px;
    }
    .container .about-card__list {
      margin-top: 20px;
    }
  }
}

@media (max-width: 680px) {
  .about-card {
    margin-top: 50px;
    background-position-y: 35%;

    .container .about-card__title {
      font-size: 40px;

      .about-card__title_description {
        font-size: 20px;
      }
    }

    .container .btn {
      width: 250px;
      height: 80px;
    }
  }
}

@media (max-width: 480px) {
  .about-card {
    background-position-y: 45%;
  }
}
</style>
