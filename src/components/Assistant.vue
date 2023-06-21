<template>
  <div class="assistant">
    <h1 class="assistant__title">Персональный помощник</h1>
    <span class="assistant__title_description">
      Бесплатно для владельцев
      <span class="assistant__title_bold">card plus</span>
    </span>
    <ul class="assistant__list">
      <div class="container">
        <li class="assistant__list-item">
          <span class="assistant__img_type_meeting"></span>
          <p class="assistant__description">
            Организует встречи, найдет гидов и переводчиков
          </p>
        </li>
        <li class="assistant__list-item">
          <span class="assistant__img_type_rout-plan"></span>
          <p class="assistant__description">
            Спланирует поездку по самым интересным местам вашего отдыха
          </p>
        </li>
        <li class="assistant__list-item">
          <span class="assistant__img_type_concert"></span>
          <p class="assistant__description">
            Достанет билеты на мероприятия, даже если их уже нет в продаже
          </p>
        </li>
        <li class="assistant__list-item">
          <span class="assistant__img_type_table-reservation"></span>
          <p class="assistant__description">
            Закажет столик в ресторане, клубе или кафе
          </p>
        </li>
      </div>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Assistant",
};
</script>

<style lang="scss" scoped>
@import "../assets/variables.scss";
@import "../assets/extends.scss";
.assistant {
  @extend %reset-default-styles;
  margin-top: 147px;

  .assistant__title {
    margin: 0 auto 12px;
    line-height: 1;
    font-size: 30px;
    font-weight: $weight-extra-bold;
    text-align: center;
  }

  .assistant__title_description {
    margin: 0 auto 60px;
    font-size: 14px;
    line-height: 1;
    font-weight: $weight-bold;
    display: block;
    text-align: center;

    .assistant__title_bold {
      color: #c0965c;
      text-transform: uppercase;
    }
  }

  .assistant__list {
    @extend %reset-default-styles;
    margin-top: 60px;
    background: url("../assets/bg-assistant.svg") -331px 0 no-repeat;
    padding: 91px 0 284.51px 530px;
    list-style-type: none;
    font-size: 14px;
    line-height: 1.43;
    font-weight: $weight-bold;
    display: flex;
    flex-direction: column;
    align-items: flex-end;

    .assistant__list-item {
      display: flex;
      column-gap: 17.82px;
      align-items: center;
      max-width: 261px;

      .assistant__description {
        max-width: 198px;
      }
    }

    .assistant__img_type_meeting {
      display: $span-img-or-description;
      background-image: url("../assets/meeting.svg");
      width: 44.18px;
      height: 44.27px;
    }

    .assistant__img_type_rout-plan {
      display: $span-img-or-description;
      background-image: url("../assets/rout-plan.svg");
      width: 43.83px;
      height: 47.86px;
    }

    .assistant__img_type_concert {
      display: $span-img-or-description;
      background-image: url("../assets/concert.svg");
      width: 44.87px;
      height: 34.68px;
    }

    .assistant__img_type_table-reservation {
      display: $span-img-or-description;
      background-image: url("../assets/table-reservation.svg");
      width: 35.2px;
      height: 42.36px;
    }
  }
}

@media (max-width: 1680px) {
  .assistant .assistant__list {
    background-position-x: -600px;
  }
}
@media (max-width: 980px) {
  .assistant {
    margin-top: 89px;

    .assistant__list {
      background-position-x: -800px;
    }
  }
}

@media screen {
  .assistant .assistant__list {
    padding-left: 300px;
  }
}

@media (max-width: 680px) {
  .assistant .assistant__list {
    background-position-x: -330px;
    background-size: 200%;
    padding: 0 0 0 165px;
    margin-bottom: 89px;

    .assistant__list-item {
      display: grid;
      grid-template-columns: 1fr 3fr;
    }
  }
  .assistant .assistant__list .assistant__img_type_meeting,
  .assistant .assistant__list .assistant__img_type_rout-plan,
  .assistant .assistant__list .assistant__img_type_concert,
  .assistant .assistant__list .assistant__img_type_table-reservation {
    background-size: 70%;
    background-repeat: no-repeat;
    background-position: right;
  }
}

@media (max-width: 480px) {
  .assistant .assistant__list {
    background: none;
    padding: 0;
    margin-bottom: 70px;
    margin-top: 20px;

    .assistant__list-item {
      display: grid;
      grid-template-columns: 1fr 3fr;
    }
  }

  .assistant .assistant__title_description {
    margin-bottom: 0;
  }
}
</style>