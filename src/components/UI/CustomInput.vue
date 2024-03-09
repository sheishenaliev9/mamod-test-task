<template>
  <div class="input-container">
    <input
      class="custom-input"
      :class="{ 'error-input': isEmpty }"
      :type="type"
      :placeholder="placeholder"
      :value="value"
      @input="updateValue"
    />
    <img
      v-if="showIcon"
      :src="iconStateType"
      alt="eye-icon"
      class="eye-icon"
      @click="toggleInputType"
    />
    <span class="error-input-text" v-if="isEmpty">{{
      samePassword ? "пароли не совпадают!" : "Это поле обязательное!"
    }}</span>
  </div>
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    type: String,
    placeholder: String,
    showIcon: Boolean,
    value: String,
    isEmpty: Boolean,
    samePassword: Boolean,
  },
  data() {
    return {
      inputValue: this.value,
    };
  },
  computed: {
    iconStateType() {
      return this.inputType === "text"
        ? require("../../assets/icons/hided.svg")
        : require("../../assets/icons/showed.svg");
    },
  },
  methods: {
    updateValue(event) {
      this.$emit("input", event.target.value);
    },
    toggleInputType() {
      this.inputType = this.inputType === "password" ? "text" : "password";
      this.$emit("toggle-password");
    },
  },
};
</script>

<style scoped>
.input-container {
  position: relative;
  width: 450px;
}

.custom-input {
  outline: none;
  padding-left: 10px;
  border: 1px solid #d9d9d9;
  width: 97%;
  height: 40px;
  border-radius: 15px;
}

.custom-input::placeholder {
  font-size: 14px;
  letter-spacing: 1px;
  color: #9292a0;
}

.eye-icon {
  position: absolute;
  cursor: pointer;
  right: 10px;
  top: 50%;
  transform: translateY(-50%);
}
.error-input {
  border: 1px solid red !important;
}

.error-input-text {
  position: absolute;
  right: 15px;
  bottom: 35px;
  padding: 0 5px;
  color: red;
  background-color: #fff;
  font-size: 12px;
}
</style>
