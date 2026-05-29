<script setup>
const cards = [
  { title: 'Оформите карту «Северяночка»', text: 'И получайте бонусы при покупке в магазинах и на сайте', image: '/products/spec1.png', orange: true },
  { title: 'Покупайте акционные товары', text: 'И получайте вдвое больше бонусов', image: '/products/spec2.png', orange: false }
]
</script>

<template>
  <section class="spec-section">
    <h2>Специальные предложения</h2>
    <div class="spec-grid">
      <div v-for="card in cards" :key="card.title" class="spec-card"
        :class="{ orange: card.orange, green: !card.orange }">
        <div class="card-info">
          <h3>{{ card.title }}</h3>
          <p>{{ card.text }}</p>
        </div>
        <img :src="card.image" alt="">
      </div>
    </div>
  </section>
</template>

<style scoped>
.spec-section {
  padding: 0 60px;
  margin-top: 80px;
}

.spec-section h2 {
  font-size: 36px;
  color: #414141;
  margin-bottom: 40px;
}

.spec-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 40px;
}

.spec-card {
  height: 200px;
  border-radius: 12px;
  padding: 30px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  overflow: hidden;
}

.orange {
  background: #FCD5BA;
}

.green {
  background: #E5FFDE;
}

.card-info {
  max-width: 260px;
}

.card-info h3 {
  font-size: 24px;
  color: #414141;
  margin-bottom: 12px;
}

.card-info p {
  font-size: 16px;
  color: #414141;
  line-height: 1.5;
}

.spec-card img {
  width: 220px;
  object-fit: contain;
}
</style>