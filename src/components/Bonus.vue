<template>
  <div class="bonus">
    <div class="container">
      <h1 class="bonus__title">Мы позаботились, чтобы вы получили</h1>

      <ul class="bonus__list">
        <li>
          <span class="bonus__img_type_unlimited-internet"></span>
          <p class="bonus__description-title">
            Бесплатный безлимитный интернет в роуминге
          </p>
          <p class="bonus__description bonus__description_type_img">
            <span class="bonus__description_image-type_megafon"></span>
            <span class="bonus__description_image-type_tele-two"></span>
            <span class="bonus__description_image-type_mts"></span>
            <span class="bonus__description_image-type_beeline"></span>
          </p>
        </li>
        <li>
          <span class="bonus__img_type_free-baggage-wrapping"></span>
          <p class="bonus__description-title">Бесплатная упаковка багажа</p>
          <p class="bonus__description bonus__description_type_text">
            Держатели карт Visa Signature могут упаковать багаж в крупных
            аэропортах России
          </p>
        </li>
        <li>
          <span class="bonus__img_type_free-app"></span>
          <p class="bonus__description-title">
            Бесплатный доступ <br />
            в приложении <br />
            App In The Air
          </p>
          <p class="bonus__description bonus__description_type_text">
            Бесплатная премиум подписка при покупке авиабилетов на
            travel.alfabank.ru
          </p>
        </li>
        <li>
          <span class="bonus__img_type_taxi-discount"></span>
          <p class="bonus__description-title">
            Такси бизнес-класса со скидкой 20%
          </p>
          <p class="bonus__description bonus__description_type_img">
            <span class="bonus__description_image-type_wheely"></span>
            <span class="bonus__description_image-type_gett"></span>
          </p>
        </li>
        <li>
          <span class="bonus__img_type_discount-restaurant"></span>
          <p class="bonus__description-title">
            Скидка в ресторанах <br />
            Novikov Group <br />
            в аэропорту Шереметьево
          </p>
        </li>
        <li>
          <span class="bonus__img_type_business-halls"></span>
          <p class="bonus__description-title">
            Доступ в бизнес-залы Priority Pass по всему миру
          </p>
        </li>
      </ul>
    </div>
  </div>
</template>
 
<script>
export default {
  name: "Bonus",
};
</script>

<style lang="scss" scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.bonus {
  @extend %reset-default-styles;
  margin-top: 169px;

  .container {
    max-width: 987px;

    .bonus__title {
      margin: 0 0 75px;
      font-weight: $weight-extra-bold;
      font-size: 30px;
      line-height: 1;
      text-align: center;
    }

    .bonus__list {
      @extend %reset-default-styles;
      display: grid;
      list-style-type: none;
      max-width: 987px;
      grid-template-columns: 1fr 1fr 1fr;
      column-gap: 65px;
      row-gap: 38px;

      .bonus__description-title {
        margin: 34px 0 0;
        font-size: 18px;
        line-height: 1;
        font-weight: $weight-extra-bold;
      }

      .bonus__img_type_unlimited-internet {
        display: inline-block;
        background-image: url("../assets/unlimited-internet.jpg");
        width: 280px;
        height: 156px;
      }

      .bonus__description {
        margin: 0;
        font-size: 14px;
        line-height: 1.43;
        font-weight: $weight-bold;
        color: #6c6c6c;

        .bonus__description_image-type_megafon {
          display: $span-img-or-description;
          background-image: url("../assets/megaphone.svg");
          width: 123px;
          height: 23px;
        }

        .bonus__description_image-type_tele-two {
          display: $span-img-or-description;
          background-image: url("../assets/tele-two.svg");
          width: 57px;
          height: 23px;
        }

        .bonus__description_image-type_mts {
          display: $span-img-or-description;
          background-image: url("../assets/mts.svg");
          width: 63px;
          height: 23px;
        }

        .bonus__description_image-type_beeline {
          display: $span-img-or-description;
          background-image: url("../assets/beeline.svg");
          width: 88px;
          height: 27px;
        }
      }

      .bonus__description_type_img {
        margin-top: 21px;
        display: flex;
        flex-wrap: wrap;
        align-items: baseline;
        row-gap: 21px;
        column-gap: 28px;
      }

      .bonus__description_type_text {
        margin-top: 7px;
      }

      .bonus__img_type_free-baggage-wrapping {
        display: $span-img-or-description;
        background-image: url("../assets/free-baggage-wrapping.jpg");
        width: 280px;
        height: 156px;
      }

      .bonus__img_type_free-app {
        display: $span-img-or-description;
        background-image: url("../assets/free-app.jpg");
        width: 280px;
        height: 156px;
      }

      .bonus__img_type_taxi-discount {
        display: $span-img-or-description;
        background-image: url("../assets/taxi-discount.jpg");
        width: 280px;
        height: 156px;
      }

      .bonus__description_image-type_wheely {
        display: $span-img-or-description;
        background-image: url("../assets/wheely.svg");
        width: 90px;
        height: 27px;
      }

      .bonus__description_image-type_gett {
        display: $span-img-or-description;
        background-image: url("../assets/gett.svg");
        width: 84px;
        height: 45px;
        background-repeat: no-repeat;
      }

      .bonus__img_type_discount-restaurant {
        display: $span-img-or-description;
        background-image: url("../assets/discount-restaurant.jpg");
        width: 280px;
        height: 156px;
      }

      .bonus__img_type_business-halls {
        display: $span-img-or-description;
        background-image: url("../assets/business-halls.jpg");
        width: 280px;
        height: 156px;
      }
    }

    .bonus__list li:nth-child(4) .bonus__description_type_img {
      column-gap: 21px;
    }

    .bonus__list li {
      max-width: 280px;
    }
  }
}
@media (max-width: 980px) {
  .bonus {
    margin-top: 89px;

    .container {
      max-width: 680px;

      .bonus__title {
        margin-bottom: 30px;
      }

      .bonus__list {
        column-gap: 30px;
        row-gap: 15px;

        .bonus__img_type_unlimited-internet,
        .bonus__img_type_free-baggage-wrapping,
        .bonus__img_type_free-app,
        .bonus__img_type_taxi-discount,
        .bonus__img_type_discount-restaurant,
        .bonus__img_type_business-halls {
          background-repeat: no-repeat;
          background-position: center;
          width: 100%;
        }

        .bonus__description-title {
          margin-top: 10px;
        }
      }
    }
  }
}

@media (max-width: 680px) {
  .bonus {
    margin-top: 70px;

    .container {
      max-width: 480px;

      .bonus__list {
        display: grid;
        grid-template-columns: 1fr 1fr;
        row-gap: 30px;

        .bonus__description-title {
          font-size: 14px;
        }

        .bonus__description {
          font-size: 12px;
        }

        .bonus__description_type_img {
          margin-top: 5px;
        }
      }
    }
  }
}

@media (max-width: 480px) {
  .bonus .container {
    max-width: 320px;
    .bonus__list {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      row-gap: 30px;
    }
  }
}
</style>
 