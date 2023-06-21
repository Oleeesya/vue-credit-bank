<template>
  <div class="footer">
    <div class="container">
      <ul class="footer__wrapper">
        <div class="footer__logo">
          <img alt="Bank logo" src="../assets/logo.svg" />
          <p class="footer__logo-name">АО «Кредит Европа Банк»</p>
        </div>

        <ul class="footer__list">
          <div class="footer__list-wrapper">
            <li>
              <a href="#" class="footer__list-item" target="_blank">О банке</a>
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Офисы и банкоматы</a
              >
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank">Новости</a>
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank">Вакансии</a>
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Реализуемое имущество</a
              >
            </li>
          </div>
          <div class="footer__list-wrapper">
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Раскрытие информации</a
              >
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Ставки по вкладам</a
              >
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Условия и тарифы</a
              >
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Корпортивное управление</a
              >
            </li>
            <li>
              <a href="#" class="footer__list-item" target="_blank"
                >Карта сайта</a
              >
            </li>
          </div>
        </ul>

        <ul class="contact">
          <li class="contact__item">
            <span>По России</span>
            <a href="”tel:+78009506570" class="contact__item-number"
              >8 800 950 6570</a
            >
          </li>
          <li class="contact__item">
            <span>По Миру</span>
            <a href="”tel:+78009506570" class="contact__item-number"
              >8 800 950 6570</a
            >
          </li>
        </ul>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Release",
};
</script>

<style lang="scss" scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.footer {
  @extend %reset-default-styles;
  margin-top: 74px;
  background: url("../assets/bg-footer.svg") repeat-x;

  .container {
    max-width: 1183px;

    .footer__wrapper {
      @extend %reset-default-styles;
      padding: 167px 0 54px;
      list-style-type: none;
      font-size: 14px;
      font-weight: $weight-medium;
      display: flex;

      .footer__logo {
        display: flex;
        flex-direction: column;
        row-gap: 15px;

        .footer__logo-name {
          margin: 0;
        }
      }
      .footer__list {
        @extend %reset-default-styles;
        margin: 0 0 0 106px;
        display: flex;
        list-style: none;
        color: #6c6c6c;
        line-height: 2.143;
        column-gap: 82px;
        max-width: 459px;

        .footer__list-item {
          color: #6c6c6c;
          text-decoration: none;
        }
      }

      .contact {
        @extend %reset-default-styles;
        margin-left: 132px;
        display: flex;
        flex-direction: column;
        row-gap: 12px;
        list-style: none;

        .contact__item {
          display: flex;
          color: #6c6c6c;
          flex-direction: column;
          row-gap: 4px;

          .contact__item-number {
            color: #bbbbbb;
            font-size: 24px;
            line-height: 1.5;
            text-decoration: none;
          }
        }
      }
    }
  }
}
@media (max-width: 1900px) {
  .footer .container {
    max-width: 1109px;
    .footer__wrapper .contact {
      margin-left: 50px;
    }
  }
}

@media (max-width: 980px) {
  .footer .container {
    max-width: 680px;

    .footer__wrapper {
      padding-top: 50px;
      column-gap: 30px;

      .footer__logo {
        max-width: 150px;
      }

      .footer__list {
        margin-left: 0;
        column-gap: 0;
      }

      .contact {
        margin-left: 0;

        .contact__item .contact__item-number {
          font-size: 15px;
        }
      }
    }
  }
}

@media (max-width: 680px) {
  .footer {
    margin-top: 0;

    .container {
      max-width: 480px;

      .footer__wrapper {
        display: flex;
        flex-direction: column;
        padding-top: 50px;
        column-gap: 30px;

        .footer__list {
          column-gap: 10px;
          display: flex;
          flex-wrap: wrap;
          row-gap: 20px;
          line-height: 1;
          margin-top: 25px;
          justify-content: space-between;
        }
        .contact,
        .footer__logo .footer__logo-name {
          display: none;
        }
      }
    }
  }
}

@media (max-width: 480px) {
  .footer .container {
    max-width: 320px;
  }
}
</style>