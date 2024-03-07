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
        <div>
          <custom-input type="string" />
          <custom-input type="email" />
        </div>
        <select name="" id=""></select>
        <div>
          <custom-input type="password" />
          <custom-input type="password" />
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

<style scoped>

</style>
