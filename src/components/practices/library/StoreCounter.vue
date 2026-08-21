<script setup>
import { useCounterStore } from '@/stores/counter.js'

const counterStore = useCounterStore()
</script>

<template>
  <div class="practice-section">
    <h2>Counter Store 활용 실습</h2>

    <p>
      원본 카운트 데이터(state): <strong>{{ counterStore.count }}</strong>
    </p>
    <p>
      2배 연산 데이터(getters): <span>{{ counterStore.doubleCount }}</span>
    </p>

    <button @click="counterStore.increment">숫자 1 증가 (actions)</button>
  </div>
</template>

<style scoped>
.practice-section {
  max-width: 500px;
  margin: 30px auto;
  padding: 24px;
  border: 1px solid #dfe3e8;
  border-radius: 10px;
}

button {
  padding: 8px 14px;
  cursor: pointer;
}
</style>
