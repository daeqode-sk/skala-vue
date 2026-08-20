<script setup>
import { ref } from 'vue'

const weatherList = ref([
  { id: 'city_01', name: '서울', temp: 28, status: '맑음' },
  { id: 'city_02', name: '수원', temp: 24, status: '비' },
  { id: 'city_03', name: '부산', temp: 26, status: '구름' },
  { id: 'city_04', name: '광주', temp: 23, status: '흐림' },
  { id: 'city_05', name: '제주', temp: 30, status: '맑음' },
])

const searchQuery = ref('')
const selectedCityInfo = ref('카드를 클릭하거나 검색해 보세요.')

const showDetail = (cityName, status) => {
  window.alert(`${cityName}의 현재 날씨는 [${status}] 상태입니다.`)
}
</script>

<template>
  <div class="dashboard-wrapper">
    <h2>🌤️ 과제 1: 날씨 (Mockup)</h2>

    <section class="search-box">
      <h3>🔍 도시 검색</h3>
      <input
        type="text"
        :value="searchQuery"
        @input="(e) => (searchQuery = e.target.value)"
        placeholder="검색할 도시 이름 입력"
      />
      <p>
        검색 중인 도시: <strong>{{ searchQuery }}</strong>
      </p>
    </section>

    <section class="list-box">
      <h3>🏙️ 지역별 날씨 현황</h3>
      <div
        v-for="item in weatherList"
        :key="item.id"
        class="weather-card"
        @click="selectedCityInfo = `${item.name}이 선택되었습니다.`"
      >
        <div class="card-info">
          <h4>{{ item.name }} ({{ item.status }})</h4>
          <p>현재 기온: {{ item.temp }}°C</p>
          <span v-if="item.temp >= 25" class="badge hot">🔥 더움 (25도 이상)</span>
          <span v-else class="badge cool">❄️ 선선함 (25도 미만)</span>
        </div>
        <button class="btn-detail" @click.stop="showDetail(item.name, item.status)">
          상세보기
        </button>
      </div>
    </section>

    <div class="status-bar">
      {{ selectedCityInfo }}
    </div>
  </div>
</template>

<style scoped>
.dashboard-wrapper {
  max-width: 500px;
  margin: 0 auto;
  font-family: sans-serif;
}
.search-box {
  background: #f8f9fa;
  padding: 16px;
  border-radius: 8px;
  margin-bottom: 20px;
}
.search-box input {
  width: 100%;
  padding: 8px 12px;
  border: 1px solid #ddd;
  border-radius: 6px;
  font-size: 14px;
  box-sizing: border-box;
}
.list-box {
  margin-bottom: 16px;
}
.weather-card {
  display: flex;
  justify-content: space-between;
  align-items: center;
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 14px 16px;
  margin-bottom: 10px;
  cursor: pointer;
  transition: box-shadow 0.2s;
  color: #333;
}
.weather-card:hover {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.12);
}
.card-info h4 {
  margin: 0 0 4px 0;
  font-weight: bold;
}
.card-info p {
  color: #555;
  font-size: 14px;
  margin: 0 0 6px 0;
}
.badge {
  display: inline-block;
  padding: 3px 10px;
  border-radius: 12px;
  font-size: 12px;
  font-weight: bold;
  color: white;
}
.hot {
  background-color: #e74c3c;
}
.cool {
  background-color: #3498db;
}
.btn-detail {
  padding: 8px 14px;
  background: #f0f0f0;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 13px;
  white-space: nowrap;
  color: #333;
}
.btn-detail:hover {
  background: #ddd;
}
.status-bar {
  background: #e8f5e9;
  border-radius: 8px;
  padding: 12px 16px;
  text-align: center;
  color: #2e7d32;
  font-weight: bold;
}
</style>
