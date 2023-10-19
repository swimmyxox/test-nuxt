<template>
  <div>
    <h1>Homa</h1>
    <ul>
      <li :style="{ color: firstItemColor }">1つ目の項目</li>
      <a>2つ目の項目</a>
      <li>3つ目の項目</li>
      <li :style="{ color: lastItemColor }">4つ目の項目</li>
    </ul>
  </div>
</template>

<script>
</script>

<script setup lang="ts">
import { ref } from 'vue'

const firstItemColor = ref('red')
const lastItemColor = ref('blue')

function makeFirstItemRed() {
  // 最初の項目の色を変更
  firstItemColor.value = 'red';
}

function makeLastItemBlue() {
  // 最後の項目の色を変更
  lastItemColor.value = 'blue';
}

function makeLastItemYellow() {
  // 最後の項目の色を変更
  lastItemColor.value = 'yellow';
}

// コンポーネントがマウントされたらメソッドを呼び出す
onMounted(() => {
  makeFirstItemRed()
  makeLastItemBlue()
})
</script>