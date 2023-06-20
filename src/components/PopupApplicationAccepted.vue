<template>
  <div
    :class="[
      this.popupAcceptedIsOpen ? 'popup_opened' : '',
      'popup_background popup',
    ]"
  >
    <div class="popup__container">
      <span class="popup__accepted-agree"></span>
      <div class="popup__title">Ваша заявка принята</div>
      <span class="popup__decription"
        >В ближайшее время с вами свяжется наш менеджер</span
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "PopupApplicationAccepted",

  props: {
    popupAcceptedIsOpen: {
      type: Boolean,
    },
  },
};
</script>

<style lang='scss' scoped>
.popup {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
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
    box-sizing: border-box;
    margin: 0 auto;
    padding: 0;
    width: 716px;
    display: flex;
    flex-direction: column;
    align-items: center;

    .popup__accepted-agree {
      display: inline-block;
      width: 32px;
      height: 20px;
      background-image: url("../assets/label-validate.svg");
      background-size: cover;
    }

    .popup__title {
      margin: 19px 0 10px;
      padding: 0;
      font-weight: 800;
      line-height: 1.133;
      font-size: 30px;
    }

    .popup__decription {
      margin: 0;
      padding: 0;
      font-size: 14px;
      line-height: 1.43;
      font-weight: 700;
      color: #6c6c6c;
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
</style>