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
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  background-color: #f5f5f5;
  font-family: "Montserrat", sans-serif;
}

#app {
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>
