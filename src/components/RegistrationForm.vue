<template>
  <form class="registration-form">
    <div class="registration-form__title">
      <h2>Регистрация</h2>
    </div>

    <div class="registration-form__inner">
      <div class="registration-form__inner__title">
        <h3>Заполните Ваши данные</h3>
      </div>

      <div class="registration-form__inner__inputs">
        <div class="registration-form__inner__inputs__block">
          <custom-input type="string" placeholder="Имя" :showIcon="false" />
          <custom-input type="email" placeholder="Email" :showIcon="false" />
        </div>

        <div class="registration-form__inner__position">
          <select v-model="selectedPosition">
            <option disabled>Должность</option>
            <option
              v-for="position in positions"
              :key="position.value"
              :value="position.name"
            >
              {{ position.name }}
            </option>
          </select>
        </div>

        <div class="registration-form__inner__inputs__block">
          <custom-input
            type="password"
            placeholder="Пароль"
            :showIcon="true"
            @toggle-password="togglePasswordIcon"
          />
          <custom-input
            type="password"
            placeholder="Повторите пароль"
            :showIcon="true"
            @toggle-password="togglePasswordIcon"
          />
        </div>
      </div>
    </div>

    <div class="registration-form__footer">
      <div class="registration-form__footer__public">
        <div class="registration-form__footer__public__slider">
          <label class="switch">
            <input type="checkbox" v-model="isChecked" />
            <span class="slider round"></span>
          </label>
        </div>
        <div class="registration-form__footer__public__title">
          <p>Хотите чтобы Ваш профиль видели другие участники платформы?</p>
          <p>Включает профиль для просмотра другими пользователями по ссылке</p>
        </div>
      </div>

      <div class="registration-form__footer__privacy">
        <div class="registration-form__footer__privacy__title">
          <input
            type="checkbox"
            class="registration-form__footer__privacy__title__checkbox"
          />
          <p class="registration-form__footer__privacy__title__text">
            Регистрируясь, Вы соглашаетесь
            <a href="#">с политикой конфиденциальности</a> и обработкой
            <a href="#">персональных данных</a>
          </p>
        </div>

        <button>Зарегистрироваться</button>
      </div>
    </div>
  </form>
</template>

<script>
import CustomInput from "./UI/CustomInput.vue";
export default {
  name: "App",
  components: {
    CustomInput,
  },
  methods: {
    togglePasswordIcon() {
      this.showPasswordIcon = !this.showPasswordIcon;
    },
  },
  data() {
    return {
      isChecked: true,
      showPasswordIcon: false,
      selectedPosition: "Должность",
      positions: [
        { value: 1, name: "Менеджер" },
        { value: 2, name: "Разработчик" },
        { value: 3, name: "Дизайнер" },
      ],
    };
  },
};
</script>

<style>
.registration-form {
  width: 960px;
  border-radius: 15px;
  background-color: #fff;
}

.registration-form__title {
  padding: 20px;
  border-bottom: 1px solid #d9d9d9;
}

.registration-form__inner {
  padding: 15px 15px 30px 30px;
  border-bottom: 1px solid #d9d9d9;
}

.registration-form__inner__title h3 {
  font-size: 16px;
  font-weight: 500;
}

.registration-form__inner__inputs {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.registration-form__inner__inputs__block {
  display: flex;
  align-items: center;
  gap: 15px;
}

.registration-form__inner__position {
  display: flex;
  justify-content: flex-end;
}
.registration-form__inner__position select {
  padding-left: 10px;
  color: #9292a0;
  font-size: 14px;
  letter-spacing: 1px;

  border: 1px solid #d9d9d9;
  outline: none;
  width: 449px;
  height: 40px;
  border-radius: 15px;
}
/* ---------------------------------------- */
/* Registration form footer */

.registration-form__footer {
  display: flex;
  flex-direction: column;
  gap: 30px;
  padding: 23px 15px 50px 30px;
}

.registration-form__footer__public {
  display: flex;
}

.registration-form__footer__public__slider {
  display: flex;
  align-items: flex-start;
}

.registration-form__footer__public__title {
  margin-left: 5px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.registration-form__footer__public__title p {
  margin: 0;
}

.registration-form__footer__public__title p:last-child {
  color: #696977;
  font-size: 14px;
}

.registration-form__footer__privacy {
  display: flex;
  justify-content: space-between;
}

.registration-form__footer__privacy__title {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  width: 66%;
}

.registration-form__footer__privacy__title__checkbox {
  transform: scale(1.5);
  cursor: pointer;
}

.registration-form__footer__privacy__title p {
  margin: 0;
}

.registration-form__footer__privacy__title p a {
  text-decoration: none;
  color: #3586ff;
}

.registration-form__footer__privacy button {
  border: none;
  outline: none;
  border-radius: 8px;
  cursor: pointer;

  width: 27%;
  color: #497ada;
  background-color: rgba(73, 122, 218, 0.2);
  transition: 0.2s;
}

.registration-form__footer__privacy button:active {
  opacity: 0.7;
}
/* ---------------------------------------- */

/* ---------------------------------------- */
/* slider */
.switch {
  position: relative;
  display: inline-block;
  width: 39px;
  height: 19px;
}

.switch input {
  display: none;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: "";
  height: 18px;
  width: 18px;
  right: 25px;
  background-color: white;
  -webkit-transition: 0.4s;
  border: 1px solid gray;
  transition: 0.4s;
}

input:checked + .slider {
  background-color: #2196f3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196f3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

/* ---------------------------------------- */
</style>
