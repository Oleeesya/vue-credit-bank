<template>
  <div class="release">
    <div class="container">
      <h1 class="release__title">Оформите свою новую карту для путешествий</h1>

      <ul class="release__list">
        <li class="release__list-item">
          <span class="release__percent">до 11%</span>
          <p class="release__description">
            Милями за услуги, оплаченные на travel.ru
          </p>
        </li>
        <li class="release__list-item">
          <span class="release__percent">до 11%</span>
          <p class="release__description">Милями за любые покупки по карте</p>
        </li>
        <li class="release__list-item">
          <span class="release__percent">1 = 1</span>
          <p class="release__description">
            Оплата милями билетов любых авиакомпаний по курсу 1 миля = 1 Р
          </p>
        </li>
      </ul>

      <div class="wrapper__release">
        <span class="release__img"></span>
        <div class="release__application">
          <div class="release__choice">
            <span class="release__choice_type_credit">Кредитная карта</span>
            <span class="release__choice_type_debit">Дебетовая карта</span>
          </div>
          <button
            type="button"
            class="release__btn_type_cend"
            v-on:click="this.openPopup"
          >
            Отправить заявку
          </button>
          <ul class="release__description">
            <li class="release__description-item">
              <span class="release__description-title"
                >Стоимость карты в год (руб.)</span
              >
              <div class="release__price">
                <span class="release__description-relation"
                  >6 490 (без пакета услуг),</span
                >
                <span class="release__description-relation"
                  >4 990 (с пакетом услуг)</span
                >
              </div>
            </li>
            <li class="release__description-item">
              <span class="release__description-title"
                >Приветственные мили (шт.)</span
              >
              <span class="release__description-relation">1 000</span>
            </li>
            <li class="release__description-item">
              <span class="release__description-title">Мили за покупки</span>
              <span class="release__description-relation">5 %</span>
            </li>
          </ul>
          <button
            type="button"
            class="release__btn_type_details"
            onClick="{onDetails}"
          >
            Все подробности
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Release",

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
.release {
  @extend %reset-default-styles;

  .container {
    max-width: 1109px;

    .release__title {
      margin: 0 auto 50px;
      line-height: 1;
      font-size: 30px;
      font-weight: $weight-extra-bold;
      text-align: center;
    }

    .release__list {
      @extend %reset-default-styles;
      list-style-type: none;
      font-size: 14px;
      line-height: 1.43;
      font-weight: $weight-bold;
      display: flex;
      justify-content: center;
      column-gap: 108px;

      .release__list-item {
        max-width: 255px;

        .release__percent {
          color: #c0965c;
          font-size: 36px;
          line-height: 1;
          font-weight: $weight-bold;
        }

        .release__description {
          color: #6c6c6c;
          font-size: 14px;
          line-height: 1.43;
          font-weight: $weight-bold;
        }
      }
    }

    .wrapper__release {
      margin-top: 84px;
      display: flex;
      justify-content: space-between;

      .release__img {
        background-image: url("../assets/card.svg");
        display: inline-block;
        width: 588px;
        height: 376px;
      }

      .release__application {
        max-width: 406px;

        .release__choice {
          display: flex;
          column-gap: 42px;
          font-size: 18px;
          line-height: 1;
          font-weight: $weight-bold;

          .release__choice_type_credit {
            color: #c0965c;
          }

          .release__choice_type_debit {
            color: #6c6c6c;
          }
        }

        .release__btn_type_cend {
          @extend %reset-default-styles;
          display: block;
          margin: 50px 0 67px;
          background-color: #c0965c;
          color: #fff;
          font-size: 24px;
          font-weight: $weight-bold;
          border: none;
          border-radius: 10px;
          width: 352px;
          height: 80px;
        }

        .release__btn_type_cend:hover {
          cursor: $cursor-hover;
        }

        .release__btn_type_details {
          @extend %reset-default-styles;
          margin-top: 27px;
          background: none;
          border: none;
          border-bottom: 1px dashed;
          color: #c0965c;
          font-size: 14px;
          line-height: 1.5;
          font-weight: $weight-medium;
        }

        .release__btn_type_details:hover {
          cursor: $cursor-hover;
        }

        .release__description {
          @extend %reset-default-styles;
          list-style: none;

          .release__description-item {
            display: grid;
            grid-template-columns: 1.15fr 1fr;
            column-gap: 25px;
            font-size: 14px;
            line-height: 1.5;
            font-weight: $weight-medium;

            .release__price {
              display: flex;
              flex-direction: column;
            }

            .release__description-title {
              color: #6c6c6c;
            }

            .release__description-relation {
              color: #bbbbbb;
            }
          }
        }
      }
    }
  }
}
</style>