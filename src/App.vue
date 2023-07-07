<template>
  <h1>QR Code Generator</h1>
  <InputContainer />
  <img src="./assets/tourists-at-victoria-falls.jpg" alt="image" />
</template>

<script setup lang="ts">
import InputContainer from "./components/InputContainer.vue";
</script>

<style lang="scss" scoped>
img {
  width: 200px;
  height: 200px;
  margin-top: 10vh;
}
</style>