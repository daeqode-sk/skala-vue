<script setup>
import { ref, onMounted } from 'vue'
import axios from 'axios'

// 💡 1. 백엔드 공용 주소
const BASE_URL = 'https://jsonplaceholder.typicode.com/posts'

// 💡 2. 반응형 상태 데이터
const items = ref([]) // 서버에서 받아온 데이터 배열 박스
const textInput = ref('') // 입력창과 연결된 글자 데이터 박스

// --------------------------------------------------
// [READ] GET : 데이터 가져오기
// --------------------------------------------------
const handleRead = async () => {
  try {
    // 공부용으로 딱 3개만 들고 옴
    const response = await axios.get(BASE_URL, { params: { _limit: 3 } })
    items.value = response.data
    console.log('GET 성공:', response.data)
  } catch (error) {
    console.error('GET 실패:', error)
  }
}

// --------------------------------------------------
// [CREATE] POST : 새 데이터 추가
// --------------------------------------------------
const handleCreate = async () => {
  try {
    const response = await axios.post(BASE_URL, {
      title: textInput.value,
      body: '내용',
      userId: 1,
    })
    console.log('POST 성공:', response.data)
    // 실제로는 DB에 저장은 안 되지만, id: 101로 응답이 옴
    items.value.unshift(response.data) // 목록 맨 앞에 추가
    textInput.value = ''
  } catch (error) {
    console.error('POST 실패:', error)
  }
}

// --------------------------------------------------
// [UPDATE] PUT : 데이터 수정
// --------------------------------------------------
const handleUpdate = async (id) => {
  try {
    const response = await axios.put(`${BASE_URL}/${id}`, {
      title: '수정된 제목',
      body: '수정된 내용',
    })
    console.log('PUT 성공:', response.data)
    // 로컬 목록도 업데이트
    const target = items.value.find((item) => item.id === id)
    if (target) target.title = '수정된 제목'
  } catch (error) {
    console.error('PUT 실패:', error)
  }
}

// --------------------------------------------------
// [DELETE] DELETE : 데이터 삭제
// --------------------------------------------------
const handleDelete = async (id) => {
  try {
    await axios.delete(`${BASE_URL}/${id}`)
    console.log('DELETE 성공')
    items.value = items.value.filter((item) => item.id !== id)
  } catch (error) {
    console.error('DELETE 실패:', error)
  }
}

// 마운트되자마자 자동으로 GET 실행
onMounted(handleRead)
</script>

<template>
  <div class="practice-section">
    <h2>⚡ Axios CRUD 프로토타입 훈련</h2>

    <!-- POST 입력창 -->
    <input v-model="textInput" placeholder="저장할 텍스트를 입력하세요" />
    <button @click="handleCreate">POST (추가)</button>

    <!-- 목록 -->
    <div v-for="item in items" :key="item.id" class="result-card">
      <p>
        <strong>ID: {{ item.id }}</strong>
      </p>
      <p>{{ item.title }}</p>
      <button @click="handleUpdate(item.id)">PUT (수정)</button>
      <button @click="handleDelete(item.id)">DEL (삭제)</button>
    </div>
  </div>
</template>
