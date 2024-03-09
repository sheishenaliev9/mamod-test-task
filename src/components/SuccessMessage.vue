<template>
  <div class="success-message-container">
    <img src="../assets/icons/success.svg" alt="succes-icon">
    <h1>{{ successMessage }}</h1>
  </div>
</template>

<script>
export default {
  name: "SuccessMessage.vue",
  props: {
    successMessage: String,
  },
};
</script>

<style>
.success-message-container {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 30px;

  height: 400px;
  width: 40%;
  border-radius: 15px;
  background-color: #fff;
}

.success-message-container img {
  width: 100px;
}
</style>
