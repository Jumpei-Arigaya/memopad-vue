<script setup>
import { ref } from 'vue'

const text = ref('')
const placeHolder = 'ここに入力'
const onInput = (e) => {
  text.value = e.target.value;
}
</script>

<template>
  <input :value='text' @input='onInput' :placeholder="placeHolder">
  <p>{{ text }}</p>
</template>