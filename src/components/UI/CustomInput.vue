<template>
  <div class="input-container">
    <input class="custom-input" :type="inputType" :placeholder="placeholder" />
    <img
      v-if="showIcon"
      :src="iconStateType"
      alt="eye-icon"
      class="eye-icon"
      @click="toggleInputType"
    />
  </div>
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    type: String,
    placeholder: String,
    showIcon: Boolean,
  },
  data() {
    return {
      inputType: this.type,
    };
  },
  methods: {
    toggleInputType() {
      this.inputType = this.inputType === "password" ? "text" : "password";
      this.$emit("toggle-password");
    },
  },
  computed: {
    iconStateType() {
      return this.inputType === "text"
        ? require("../../assets/icons/hided.svg")
        : require("../../assets/icons/showed.svg");
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
</style>
