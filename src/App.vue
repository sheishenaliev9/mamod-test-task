<template>
  <div id="app">
    <registration-form
      v-if="!isSuccess"
      @registration-success="handleRegistrationSuccess"
    />
    <success-message v-else success-message="Регистрация успешно прошла!" />
  </div>
</template>

<script>
import RegistrationForm from "./components/RegistrationForm.vue";
import SuccessMessage from "./SuccessMessage.vue";

export default {
  name: "App",
  components: {
    RegistrationForm,
    SuccessMessage,
  },
  methods: {
    handleRegistrationSuccess() {
      this.isSuccess = true;
    },
  },
};
</script>

<style>
html {
  font-family: "Montserrat", sans-serif;
}

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #f5f5f5;
}

#app {
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
