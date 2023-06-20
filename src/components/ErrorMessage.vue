<template>
  <span class="error">
    {{ message }}
  </span>
</template>

<script>
export default {
  name: "ErrorMessage",
  props: {
    message: {
      type: String,
    },
  },
};
</script>

<style>
.error {
  margin: 10px 0 0 30px;
  display: flex;
  color: red;
  font-size: 12px;
  font-weight: 500;
  line-height: 1.13;
}
</style>