<script setup>
const articles = [
  { image: '/products/state1.png', date: '05.03.2021', title: 'Режим использования масок и перчаток на территории магазинов', text: 'Подробная информация о режимах использования масок и перчаток на территории магазинов "ЛЕНТА". Информация обновляется каждый будний день.' },
  { image: '/products/state2.png', date: '05.03.2021', title: 'Весеннее настроение для каждой', text: '8 Марта — это не просто Международный женский день, это ещё день тюльпанов, приятных сюрпризов и праздничных тёплых пожеланий.' },
  { image: '/products/state3.png', date: '22.02.2020', title: 'ЗОЖ или ФАСТФУД. А вы на чьей стороне? Голосуем!', text: 'Голосуйте за любимые категории, выбирайте категорию-победителя в мобильном приложении и получайте кешбэк 10% баллами в апреле!' }
]
</script>

<template>
  <section class="articles-section">
    <div class="top">
      <h2>Статьи</h2>
      <div class="all">Все статьи →</div>
    </div>
    <div class="articles-grid">
      <div class="article-card" v-for="article in articles" :key="article.title">
        <img :src="article.image" alt="">
        <div class="article-content">
          <span>{{ article.date }}</span>
          <h3>{{ article.title }}</h3>
          <p>{{ article.text }}</p>
          <button>Подробнее</button>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.articles-section {
  padding: 0 60px;
  margin-top: 100px;
}

.top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 40px;
}

.top h2 {
  font-size: 36px;
  color: #414141;
}

.all {
  color: #606060;
  cursor: pointer;
}

.articles-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 40px;
}

.article-card {
  background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 2px 10px rgba(0,0,0,0.06);
}

.article-card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

.article-content {
  padding: 20px;
}

.article-content span {
  font-size: 12px;
  color: #8f8f8f;
}

.article-content h3 {
  margin-top: 14px;
  font-size: 22px;
  color: #414141;
  line-height: 1.4;
}

.article-content p {
  margin-top: 14px;
  line-height: 1.5;
  color: #606060;
  min-height: 100px;
}

.article-content button {
  width: 150px;
  height: 40px;
  border: none;
  border-radius: 6px;
  background: #E5FFDE;
  color: #70C05B;
  cursor: pointer;
  font-size: 16px;
}
</style>