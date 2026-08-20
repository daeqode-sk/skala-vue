<script setup>
// 1. 부모로부터 주입받을 데이터의 자료형 및 필수 여부 정의
defineProps({
  parentData: {
    type: String,
    required: true,
  },
})

// 2. 부모로 송신할 커스텀 이벤트 식별자 등록
const emit = defineEmits(['update-request'])

// 3. 버튼 클릭 시 페이로드를 실어 부모로 이벤트 디스패치
const sendNotification = () => {
  const payload = 'Child에서 가공한 새로운 데이터'
  emit('update-request', payload)
}
</script>

<template>
  <div class="child-container">
    <h2>하위 컴포넌트 (Child)</h2>
    <p>
      수신된 Props 데이터: <strong>{{ parentData }}</strong>
    </p>
    <br />
    <button @click="sendNotification">상위 컴포넌트로 갱신 요청 (Emit)</button>
  </div>
</template>

<style scoped>
.child-container {
  background: #f0f9ff;
  border: 1px solid #bae6fd;
  border-radius: 8px;
  padding: 16px;
  margin-top: 12px;
}
</style>
