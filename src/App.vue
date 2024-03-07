<template>
  <div id="app">
    <registration-form />
  </div>
</template>

<script>
import RegistrationForm from "./components/RegistrationForm.vue";

export default {
  name: "App",
  components: {
    RegistrationForm,
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
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
