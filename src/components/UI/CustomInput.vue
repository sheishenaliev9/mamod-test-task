<template>
  <input class="custom-input" :type="type" :placeholder="placeholder" />
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    type: String,
    placeholder: String,
  },
};
</script>

<style>
.custom-input {
  padding-left: 10px;
  border: 1px solid #d9d9d9;
  width: 450px;
  height: 40px;
  border-radius: 15px;
}

.custom-input::placeholder {
  font-size: 14px;
  letter-spacing: 1px;
  color: #9292a0;
}
</style>
