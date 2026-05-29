<script setup>
const tabs = ['п.Щельяюр', 'д.Вертеп', 'с.Краснобор', 'д.Диюр']
</script>

<template>
  <section class="shop-section">
    <h2>Наши магазины</h2>
    <div class="tabs">
      <button v-for="tab in tabs" :key="tab" :class="tab === 'п.Щельяюр' ? 'active' : ''">
        {{ tab }}
      </button>
    </div>
    <div class="map">
      <img src="/products/map.png" alt="">
    </div>
  </section>
</template>

<style scoped>
.shop-section {
  padding: 0 60px;
  margin-top: 100px;
}

.shop-section h2 {
  font-size: 36px;
  color: #414141;
  margin-bottom: 40px;
}

.tabs {
  display: flex;
  gap: 16px;
  margin-bottom: 30px;
}

.tabs button {
  border: none;
  background: #F3F2F1;
  padding: 12px 24px;
  border-radius: 6px;
  cursor: pointer;
  font-size: 14px;
  color: #606060;
}

.tabs .active {
  background: #70C05B;
  color: white;
}

.map {
  width: 100%;
  height: 420px;
  border-radius: 12px;
}

.map img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>