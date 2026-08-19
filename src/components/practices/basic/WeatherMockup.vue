<script setup>
import { ref } from 'vue'

const weatherList = ref([
  { id: 'city_01', name: '서울', temp: 28, status: '맑음' },
  { id: 'city_02', name: '수원', temp: 24, status: '비' },
  { id: 'city_03', name: '부산', temp: 26, status: '구름' },
  { id: 'city_04', name: '제주', temp: 30, status: '맑음' },
  { id: 'city_05', name: '강릉', temp: 27, status: '흐림' },
])
</script>

<template>← 여기에 화면 HTML 작성</template>

<style scoped>
← 여기에 CSS 작성
</style>
