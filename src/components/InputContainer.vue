<template>
  <div class="container">
    <input type="text" placeholder="http:// ..." ref="QRurl" />
    <input type="file" id="background" accept="image/*" ref="IMGurl" />
    <button @click="submit()">GENERATE</button>
  </div>
</template>

<script lang="ts" setup>
import { ref, defineEmits } from "vue";

const QRurl = ref();
const IMGurl = ref();
const emit = defineEmits<{
  url: [value: string];
}>();

function submit() {
  emit(
    "url",
    QRurl.value.value,
    IMGurl.value.files[0]
      ? URL.createObjectURL(IMGurl.value.files[0])
      : "./src/assets/back.jpg"
  );
}
</script>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 40%;
  height: 20vh;
  padding: 1rem;
  border-radius: 1rem;
  box-shadow: 0 0 10px white;

  input[type="text"] {
    border-radius: 5rem;
    padding: 0.5rem 1rem;
    font-size: large;
  }

  button {
    border-radius: 8px;
    border: 1px solid transparent;
    padding: 0.6em 1.2em;
    font-size: 1em;
    font-weight: 500;
    font-family: inherit;
    background-color: #1a1a1a;
    color: white;
    cursor: pointer;
    transition: border-color 0.25s;

    &:hover {
      border-color: #646cff;
    }

    &:focus,
    &:focus-visible {
      outline: 4px auto -webkit-focus-ring-color;
    }
  }
}
</style>