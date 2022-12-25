<script setup>
import { ref } from 'vue'

const text = ref('')
const placeHolder = 'ここに入力'
const awesome = ref(false)
const onClickToggle = () => {
  awesome.value = !awesome.value
}
const newTodo = ref('');
let id = 0;
const todos = ref([
  { id: id++, text: 'HTMLの勉強' },
  { id: id++, text: 'Typescriptのコーディング' },
  { id: id++, text: 'キャンプ用品の準備' },
])

const addTodo = () => {
  todos.value.push({ id: 1, text: '新規追加分' })
}

console.log(todos)

</script>

<template>
  <input v-model="text" :placeholder="placeHolder">
  <p>{{ text }}</p>
  <button @click="onClickToggle">切り替えボタン</button>
  <h1 v-if="awesome">切り替え表示領域</h1>
  <h1 v-else>oh...(^o^)</h1>

  <ul>
    <li v-for="todo in todos" :key="todo.id">{{ todo.text }}</li>
  </ul>
</template>