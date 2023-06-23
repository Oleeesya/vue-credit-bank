<template>
  <div
    :class="[this.popupIsOpen ? 'popup_opened' : '', 'popup_background popup']"
  >
    <div class="popup__container">
      <form class="popup__form" :onSubmit="createdCard">
        <div class="popup__form-header">
          <button
            class="popup__close-button"
            type="button"
            v-on:click="this.closePopup"
          ></button>
          <h2 class="popup__form-title">Заявка на карту</h2>
        </div>
        <label class="popup__label">
          <div class="popup__input-wrapper">
            <input
              :class="[
                fillDataErrorFullName ? 'popup__input_error' : '',
                'popup__input',
              ]"
              id="title-input"
              type="text"
              name="name"
              required
              maxLength="40"
              minLength="5"
              placeholder="ФИО"
              v-model="fullName"
              @change="validateFullName"
              @input="clearErrorFullName"
              @mouseover="handler"
              @mouseout="handlerOut"
            /><span
              :class="[
                fillDataErrorFullName
                  ? 'popup__label_check_error'
                  : fillDataValidateFullName
                  ? 'popup__label_check_validate'
                  : '',
                '',
              ]"
            ></span>
          </div>
          <ErrorMessage :message="fillDataErrorFullName" />
        </label>
        <label class="popup__label">
          <div class="popup__input-wrapper">
            <input
              :class="[
                fillDataErrorEmail ? 'popup__input_error' : '',
                'popup__input',
              ]"
              id="subtitle-input"
              type="text"
              name="email"
              required
              maxLength="200"
              minLength="3"
              placeholder="Электронный адрес"
              v-model="email"
              @change="validateEmail"
              @input="clearErrorEmail"
              @mouseover="handler"
              @mouseout="handlerOut"
            /><span
              :class="[
                fillDataErrorEmail
                  ? 'popup__label_check_error'
                  : fillDataValidateEmail
                  ? 'popup__label_check_validate'
                  : '',
                '',
              ]"
            ></span>
          </div>
          <ErrorMessage :message="fillDataErrorEmail" />
        </label>
        <label class="popup__label">
          <div class="popup__input-wrapper">
            <input
              :class="[
                fillDataErrorNumberPhone ? 'popup__input_error' : '',
                'popup__input',
              ]"
              id="subtitle-input"
              type="text"
              name="phone"
              required
              maxLength="200"
              minLength="2"
              placeholder="Номер телефона"
              v-model="numberPhone"
              @change="validateNumberPhone"
              @input="clearErrorNumberPhone"
              @mouseover="handler"
              @mouseout="handlerOut"
            /><span
              :class="[
                fillDataErrorNumberPhone
                  ? 'popup__label_check_error'
                  : fillDataValidateNumberPhone
                  ? 'popup__label_check_validate'
                  : '',
                '',
              ]"
            ></span>
          </div>
          <ErrorMessage :message="fillDataErrorNumberPhone" />
        </label>
        <div class="popup__label">
          <div class="popup__input-wrapper">
            <span class="popup__title_type_nationality">Гражданство</span>
            <div class="popup__label_type_select" tabindex="1">
              <div v-for="item in this.arrayCountry" v-bind:key="item.id">
                <input
                  v-if="item.name == this.country.name"
                  class="popup__input_select-opt"
                  :name="this.country.name"
                  type="radio"
                  :id="this.country.id"
                  checked
                />
                <label
                  v-if="item.name == this.country.name"
                  :for="[this.country.id]"
                  class="popup__label_select-item"
                >
                  {{ this.country.name }}
                </label>
                <input
                  v-if="item.name !== this.country.name"
                  class="popup__input_select-opt"
                  :name="item.name"
                  type="radio"
                  :id="item.id"
                  @change="checkedSelect"
                />
                <label
                  v-if="item.name !== this.country.name"
                  :for="item.id"
                  class="popup__label_select-item"
                >
                  {{ item.name }}
                </label>
              </div>
            </div>
          </div>
        </div>
        <div class="agree">
          <input
            type="checkbox"
            id="agree"
            class="agree__checkbox_type_custom"
            value="Я соглашаюсь на обработку моих персональных данных"
            @change="agreeClick"
          />
          <label for="agree" class="agree__checkbox_type_new"></label>
          <span class="agree__description"
            >Я соглашаюсь на
            <span class="agree__description_bold">обработку</span> моих
            персональных данных</span
          >
        </div>
        <button
          type="submit"
          :class="[
            fillDataValidateFullName &&
            fillDataValidateEmail &&
            fillDataValidateNumberPhone &&
            fillAgree
              ? 'popup__form-submit'
              : '',
            'popup__form-submit_error',
          ]"
          class="popup__form-submit_error"
        >
          Заказать сейчас
        </button>
      </form>
    </div>
  </div>
  <PopupApplicationAccepted :popupAcceptedIsOpen="popupAcceptedIsOpen" />
</template>

<script>
import ErrorMessage from "./ErrorMessage.vue";
import PopupApplicationAccepted from "./PopupApplicationAccepted.vue";

export default {
  name: "PopupWithForm",

  components: {
    ErrorMessage,
    PopupApplicationAccepted,
  },

  props: {
    popupIsOpen: {
      type: Boolean,
    },
  },
  emits: ["closePopup"],

  data() {
    return {
      fullName: "",
      email: "",
      numberPhone: "",
      fillDataErrorFullName: "",
      fillDataErrorEmail: "",
      fillDataErrorNumberPhone: "",
      fillDataValidateFullName: false,
      fillDataValidateEmail: false,
      fillDataValidateNumberPhone: false,
      fillAgree: false,
      popupAcceptedIsOpen: false,
      country: { id: "option1", name: "Российская федерация" },
      arrayCountry: [
        { id: "option1", name: "Российская федерация" },
        { id: "option2", name: "Беларусь" },
        { id: "option3", name: "Украина" },
        { id: "option4", name: "Казахстан" },
      ],
    };
  },

  methods: {
    closePopup() {
      this.$emit("closePopup");
    },

    validateFullName() {
      if (
        this.fullName === "" ||
        /[^а-яА-Я ]+$/.test(this.fullName) ||
        this.fullName.length < 5
      ) {
        this.fillDataErrorFullName = "Некорректно введены данные";
        return;
      } else {
        this.fillDataValidateFullName = true;

        return true;
      }
    },

    validateEmail() {
      if (!/^\S+@\S+\.\S+$/.test(this.email) || this.email === "") {
        this.fillDataErrorEmail = "Некорректно введены данные";
        return;
      } else {
        this.fillDataValidateEmail = true;

        return true;
      }
    },

    validateNumberPhone() {
      if (
        !/\(?([0-9]{3})\)?([ .-]?)([0-9]{3})\2([0-9]{4})/.test(
          this.numberPhone
        ) ||
        this.numberPhone === ""
      ) {
        this.fillDataErrorNumberPhone = "Некорректно введены данные";
        return;
      } else {
        this.fillDataValidateNumberPhone = true;

        return true;
      }
    },

    clearErrorFullName() {
      this.fillDataErrorFullName = "";
      this.fillDataValidateFullName = undefined;
    },
    clearErrorEmail() {
      this.fillDataErrorEmail = "";
      this.fillDataValidateEmail = undefined;
    },
    clearErrorNumberPhone() {
      this.fillDataErrorNumberPhone = "";
      this.fillDataValidateNumberPhone = undefined;
    },

    handler(event) {
      event.target.classList.add("popup__input_bg");
    },
    handlerOut(event) {
      event.target.classList.remove("popup__input_bg");
    },
    agreeClick(e) {
      if (e.target.checked) {
        this.fillAgree = true;
      } else {
        this.fillAgree = false;
      }
    },
    checkedSelect(e) {
      this.country = e.target;
      this.arrayCountry.sort((a, b) => {
        if (a.name === this.country.name) {
          return -1;
        } else if (a > b) {
          return -1;
        } else return 1;
      });
    },

    createdCard(e) {
      if (
        !this.validateFullName() ||
        !this.validateEmail() ||
        !this.validateNumberPhone() ||
        !this.fillAgree
      ) {
        e.preventDefault();
      } else if (
        this.validateFullName() &&
        this.validateEmail() &&
        this.validateNumberPhone() &&
        this.fillAgree
      ) {
        e.preventDefault();
        this.popupAcceptedIsOpen = true;
      }
    },
  },
};
</script>

<style lang='scss' scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.popup {
  @extend %reset-default-styles;

  position: fixed;
  z-index: 100;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  opacity: 0;
  visibility: hidden;
  transition: visibility 0.5s, opacity 0.5s linear;

  .popup__container {
    @extend %reset-default-styles;
    width: 716px;

    .popup__form {
      display: flex;
      flex-direction: column;
      row-gap: 20px;

      .popup__form-header {
        @extend %reset-default-styles;
        position: relative;
        max-width: 680px;
        width: 100%;
      }

      .popup__form-title {
        margin: 0 auto 30px;
        font-weight: 800;
        line-height: 1.133;
        font-size: 30px;
        color: #fff;
        text-align: center;
      }

      .agree {
        display: flex;
        align-items: center;
        margin-top: 20px;

        .agree__checkbox_type_custom {
          position: absolute;
          z-index: -1;
          opacity: 0;
          width: 39px;
          height: 39px;
        }

        .agree__checkbox_type_new {
          display: inline-flex;
          align-items: center;
          user-select: none;
        }

        .agree__checkbox_type_new::before {
          content: "";
          display: inline-block;
          width: 39px;
          height: 39px;
          border-radius: 10px;
          background: #333333;
        }

        .agree__checkbox_type_new:hover {
          cursor: $cursor-hover;
        }

        .agree__checkbox_type_custom:checked
          + .agree__checkbox_type_new::before {
          background-image: url("../assets/check-agree.svg");
          background-repeat: no-repeat;
          background-position: center;
        }

        .agree__description {
          color: #6c6c6c;
          font-size: 16px;
          font-weight: $weight-medium;
          line-height: 1.125;
          margin-left: 20px;

          .agree__description_bold {
            color: #fff;
          }
        }
      }

      .popup__form-submit_error {
        display: block;
        margin: 9px 0 0;
        background-color: #191919;
        color: #474747;
        font-size: 24px;
        font-weight: $weight-bold;
        line-height: 1.132;
        border: none;
        border-radius: 10px;
        width: 290px;
        height: 80px;
      }

      .popup__form-submit {
        background-color: #c0965c;
        color: #fff;
      }

      .popup__form-submit:hover {
        cursor: $cursor-hover;
      }

      .popup__label_type_select {
        display: flex;
        flex-direction: column;
        position: relative;
        width: 100%;
        max-width: 680px;

        .popup__label_select-item {
          padding: 40px 29px 21px 30px;
          display: flex;
          align-items: center;
          border-top: #222 solid 1px;
          position: absolute;
          top: 0;
          width: 100%;
          pointer-events: none;
          order: 2;
          z-index: 1;
          font-weight: $weight-medium;
          font-size: 20px;
          line-height: 1.132;
          background: #191919;
          border-radius: 10px;
          box-sizing: border-box;
          overflow: hidden;
          white-space: nowrap;
        }

        .popup__label_select-item:checked {
          border-radius: 10px;
        }

        .popup__input_select-opt {
          opacity: 1;
          position: absolute;
          left: 99px;
          top: 0;
        }

        .popup__input_select-opt:checked + label {
          order: 2;
          z-index: 2;
          border-top: none;
          position: relative;
          font-weight: 500;
          font-size: 20px;
          line-height: 1.132;
        }

        .popup__input_select-opt:checked + label:after {
          content: url("../assets/arrow-select.svg");
          transform: rotate(180deg);
          position: absolute;
          right: 31px;
          z-index: 3;
          top: 36px;
        }
      }

      .popup__label_type_select:hover {
        cursor: pointer;
      }

      .popup__label_type_select:focus .popup__label_select-item {
        position: relative;
        top: 0;
        pointer-events: all;
        background: #333333;
        cursor: pointer;
      }

      .popup__label_type_select:focus
        .popup__input_select-opt:checked
        + label:after {
        transform: rotate(0deg);
      }
    }

    .popup__close-button {
      @extend %reset-default-styles;
      position: absolute;
      right: 0;
      top: -10px;
      cursor: $cursor-hover;
      border: none;
      background: none;
      width: 65px;
      height: 60px;
      background-image: url("../assets/btn-close-popup.svg");
      background-size: cover;
    }

    .popup__input-wrapper {
      display: flex;
      align-items: center;
      column-gap: 20px;
      position: relative;

      .popup__input {
        box-sizing: border-box;
        margin: 0;
        padding: 31px 29px 30px 30px;
        width: 100%;
        max-width: 680px;
        font-weight: $weight-medium;
        font-size: 20px;
        line-height: 1.132;
        border: none;
        border-bottom: 1px solid rgba(0, 0, 0, 0.2);
        border-radius: 10px;
        background: #191919;
        color: #fff;
      }

      .popup__input_bg {
        background: #333333;
      }

      .popup__input_error {
        border: 2px solid #cc301b;
      }

      .popup__label_check_error {
        width: 16px;
        height: 16px;
        background-image: url("../assets/label-error.svg");
        background-size: cover;
      }

      .popup__label_check_validate {
        width: 19.5px;
        height: 12px;
        background-image: url("../assets/label-validate.svg");
        background-size: cover;
      }

      .popup__title_type_nationality {
        position: absolute;
        margin: 0 0 0 30px;
        padding: 0;
        font-size: 14px;
        line-height: 1.132;
        font-weight: $weight-medium;
        color: #6c6c6c;
        z-index: 3;
        top: 15px;
      }

      .popup__input_type_nationality {
        color: #fff;
        padding-top: 45px;
        padding-bottom: 16px;
      }
    }
  }
}
.popup_opened {
  visibility: visible;
  opacity: 1;
}
.popup_background {
  background: #000000;
}

@media (max-width: 680px) {
  .popup .popup__container {
    width: 480px;
  }
}
@media (max-width: 480px) {
  .popup .popup__container {
    width: 320px;
  }
  .popup .popup__container .popup__form .popup__form-title {
    font-size: 25px;
  }
}
</style>