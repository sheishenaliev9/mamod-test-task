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
          <custom-input type="string" placeholder="Имя" />
          <custom-input type="email" placeholder="Email" />
        </div>
        <select name="" id=""></select>
        <div class="registration-form__inner__inputs__block">
          <custom-input type="password" placeholder="Пароль" />
          <custom-input type="password" placeholder="Повторите пароль" />
        </div>
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
};
</script>

<style>
.registration-form {
  width: 960px;
  height: 547px;
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
  font-weight: medium;
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
</style>
