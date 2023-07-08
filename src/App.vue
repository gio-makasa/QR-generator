<template>
  <h1>QR Code Generator</h1>
  <InputContainer @getURL="getURL" />
  <div class="result">
    <img
      src="https://e0.pxfuel.com/wallpapers/933/367/desktop-wallpaper-anime-nature-green-anime-scenery.jpg"
      alt="background"
      id="background"
    />
    <img
      :src="
        'https://api.qrserver.com/v1/create-qr-code/?size=150x150&data=' + url
      "
      alt="image"
      id="qr"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import InputContainer from "./components/InputContainer.vue";

const url = ref("https://gio-makasa.github.io");

function getURL(data: string) {
  url.value = data;
}
</script>

<style lang="scss" scoped>
.result {
  position: relative;
  width: 300px;
  height: 300px;
  margin-top: 10vh;

  #background {
    width: 100%;
    height: 100%;
  }

  #qr {
    position: absolute;
    width: 150px;
    height: 150px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
    opacity: 0.8;
  }
}
</style>