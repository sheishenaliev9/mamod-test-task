<template>
  <input :type="type" />
</template>

<script>
export default {
    name: "CustomInput",
    props: {
        type: String
    }
};
</script>

<style scoped></style>
