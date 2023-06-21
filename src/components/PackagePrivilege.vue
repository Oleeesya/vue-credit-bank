<template>
  <div class="package-privilege">
    <div class="container">
      <h1 class="package-privilege__title">
        Путешествие мечты начинается с CARD PLUS
      </h1>
      <span class="package-privilege__title_description">
        Мы продумали каждую мелочь. Владельцы CARD PLUS получают особый пакет
        привилегий, необходимый для любого путешествия
      </span>

      <ul class="package-privilege__list">
        <li>
          <span class="package-privilege__img_type_ticket"></span>
          <p class="package-privilege__description-title">
            Билеты любых авиакомпаний
          </p>
          <p class="package-privilege__description">
            Предложения от 300+ авиакомпаний, 185+ lowcost перевозчиков, чартеры
            от 60 крупных российскихтуроператоров
          </p>
        </li>
        <li>
          <span class="package-privilege__img_type_avia"></span>
          <p class="package-privilege__description-title">
            Мили больше не сгорают
          </p>
          <p class="package-privilege__description">
            Мили, накопленные при оплате картой AlfaTravel, не сгорают и
            остаются на вашем счете, пока вы не решите их потратить
          </p>
        </li>
        <li>
          <span class="package-privilege__img_type_insurance"></span>
          <p class="package-privilege__description-title">
            Продвинутая страховка – бесплатно
          </p>
          <p class="package-privilege__description">
            Расширенная страховка для всей семьи с учетом экстремальных видов
            спорта и алкоголя
          </p>
        </li>
        <li>
          <span class="package-privilege__img_type_account-money"></span>
          <p class="package-privilege__description-title">
            Доступ к счетам в разных валютах
          </p>
          <p class="package-privilege__description">
            Текущие счета в рублях, долларах США, евро, английских фунтах
            стерлингов и швейцарских франках открываются в любой момент
          </p>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "AboutCard",
};
</script>

<style lang="scss" scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.package-privilege {
  @extend %reset-default-styles;
  max-width: 1008.34px;

  .package-privilege__title {
    margin: 0;
    line-height: 1;
    font-size: 30px;
    font-weight: $weight-extra-bold;
    text-align: center;
  }

  .package-privilege__title_description {
    margin: 8px auto 81.08px;
    font-size: 14px;
    line-height: 1;
    color: #6c6c6c;
    display: block;
    font-weight: $weight-bold;
    text-align: center;
    max-width: 530px;
  }

  .package-privilege__list {
    @extend %reset-default-styles;
    margin-top: 84px;
    list-style-type: none;
    font-weight: $weight-bold;
    display: flex;
    justify-content: center;

    .package-privilege__img_type_ticket {
      margin-bottom: 23px;
      display: $span-img-or-description;
      background-image: url("../assets/ticket.svg");
      width: 56.34px;
      height: 54.36px;
      background-repeat: no-repeat;
    }

    .package-privilege__img_type_avia {
      margin-bottom: 22.99px;
      display: $span-img-or-description;
      background-image: url("../assets/avia.svg");
      width: 58.38px;
      height: 57.93px;
      background-repeat: no-repeat;
    }

    .package-privilege__img_type_insurance {
      margin-bottom: 22.99px;
      display: $span-img-or-description;
      background-image: url("../assets/insurance.svg");
      width: 58.21px;
      height: 52.13px;
      background-repeat: no-repeat;
    }

    .package-privilege__img_type_account-money {
      margin-bottom: 22px;
      display: $span-img-or-description;
      background-image: url("../assets/account-money.svg");
      width: 57.97px;
      height: 55.98px;
      background-repeat: no-repeat;
    }

    .package-privilege__description-title {
      margin: 0 0 18px;
      font-size: 18px;
      font-weight: $weight-extra-bold;
      line-height: 1;
    }

    .package-privilege__description {
      margin: 0;
      font-size: 14px;
      font-weight: $weight-bold;
      color: #6c6c6c;
    }
  }

  .package-privilege__list li {
    max-width: 199px;
  }

  .package-privilege__list li:first-child {
    margin-right: 72px;
  }
  .package-privilege__list li:not(:first-child):not(:last-child) {
    margin-right: 64px;
  }
}
@media (max-width: 1900px) {
  .package-privilege .package-privilege__list {
    padding: 0 1px;
  }
}
@media (max-width: 980px) {
  .package-privilege .package-privilege__title {
    font-size: 34px;
  }
  .package-privilege
    .package-privilege__list
    li[data-v-779edbbb]:not(:first-child):not(:last-child) {
    margin-right: 0;
  }
  .package-privilege .package-privilege__list li[data-v-779edbbb]:first-child {
    margin-right: 0;
  }
  .package-privilege .package-privilege__list {
    column-gap: 20px;
    margin-top: 55px;
  }
  .package-privilege .package-privilege__title_description {
    margin: 30px auto 0;
  }
}

@media (max-width: 680px) {
  .package-privilege .package-privilege__list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    row-gap: 10px;

    .package-privilege__description-title {
      font-size: 14px;
    }
    .package-privilege__description {
      font-size: 12px;
    }
  }
}
</style>
