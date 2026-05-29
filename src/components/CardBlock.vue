<script setup>
const sections = [
  {
    title: 'Акции',
    products: [
      { image: '/products/blini.jpg', price: '44,50 ₽', oldPrice: '50,50 ₽', name: 'Г/Ц Блинчики с мясом вес.', sale: '-50%', active: false },
      { image: '/products/moloko.jpg', price: '44,50 ₽', oldPrice: '50,50 ₽', name: 'Молоко ПРОСТОКВАШИНО паст.', sale: '-50%', active: false },
      { image: '/products/kolbasa1.jpg', price: '44,50 ₽', oldPrice: '50,50 ₽', name: 'Колбаса сырокопченая МЯСНАЯ ИСТОРИЯ', sale: '-50%', active: true },
      { image: '/products/sosiski.jpg', price: '44,50 ₽', oldPrice: '50,50 ₽', name: 'Сосиски вареные МЯСНАЯ ИСТОРИЯ', sale: '-50%', active: false }
    ]
  },
  {
    title: 'Новинки',
    products: [
      { image: '/products/kolbasa2.jpg', price: '599,99 ₽', oldPrice: '', name: 'Колбаса сырокопченая ДЕСНА-ПОЛЕСЬЕ', sale: '', active: false },
      { image: '/products/kolbasa1.jpg', price: '44,50 ₽', oldPrice: '', name: 'Колбаса сырокопченая МЯСНАЯ ИСТОРИЯ', sale: '', active: true },
      { image: '/products/sosiski.jpg', price: '159,99 ₽', oldPrice: '', name: 'Сосиски вареные МЯСНАЯ ИСТОРИЯ', sale: '', active: false },
      { image: '/products/moloko.jpg', price: '49,39 ₽', oldPrice: '', name: 'Молоко ПРОСТОКВАШИНО паст.', sale: '', active: false }
    ]
  },
  {
    title: 'Покупали раньше',
    products: [
      { image: '/products/vetchina.jpg', price: '77,99 ₽', oldPrice: '', name: 'Ветчина ДОМАШНЯЯ', sale: '', active: false },
      { image: '/products/sosiski.jpg', price: '159,99 ₽', oldPrice: '', name: 'Сосиски вареные МЯСНАЯ ИСТОРИЯ', sale: '', active: false },
      { image: '/products/kolbasa2.jpg', price: '599,99 ₽', oldPrice: '', name: 'Колбаса сырокопченая ДЕСНА-ПОЛЕСЬЕ', sale: '', active: false },
      { image: '/products/moloko.jpg', price: '49,39 ₽', oldPrice: '', name: 'Молоко ПРОСТОКВАШИНО паст.', sale: '', active: false }
    ]
  }
]
</script>

<template>
  <div class="card-wrapper">
    <section v-for="section in sections" :key="section.title" class="products-section">
      <div class="section-top">
        <h2>{{ section.title }}</h2>
        <div class="all-link">
          <span>Все {{ section.title }}</span>
          <span>›</span>
        </div>
      </div>

      <div class="products-grid">
        <div class="product-card" v-for="product in section.products" :key="product.name">
          <div class="product-image">
            <img :src="product.image" alt="" />
            <div v-if="product.sale" class="sale">{{ product.sale }}</div>
            <div class="heart">
              <svg width="22" height="20" viewBox="0 0 22 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path fill-rule="evenodd" clip-rule="evenodd"
                  d="M11.6577 1.75827C12.783 0.632497 14.3095 0 15.9013 0C17.493 0 19.0195 0.632466 20.1448 1.75819C21.2705 2.88347 21.9031 4.41012 21.9031 6.00183C21.9031 7.59357 21.2706 9.12009 20.1448 10.2454C20.1448 10.2454 20.1449 10.2454 20.1448 10.2454L11.3048 19.0854C11.1096 19.2806 10.793 19.2806 10.5977 19.0854L1.75774 10.2454C-0.585912 7.90173 -0.585912 4.10192 1.75774 1.75827C4.10139 -0.585378 7.90119 -0.585378 10.2448 1.75827L10.9513 2.46472L11.6577 1.75827C11.6578 1.75824 11.6577 1.7583 11.6577 1.75827ZM15.9013 1C14.5748 1 13.3027 1.52711 12.3649 2.4653L11.3048 3.52538C11.2111 3.61915 11.0839 3.67183 10.9513 3.67183C10.8187 3.67183 10.6915 3.61915 10.5977 3.52538L9.53774 2.46538C7.58461 0.512254 4.41797 0.512254 2.46484 2.46538C0.511719 4.4185 0.511719 7.58515 2.46484 9.53827L10.9513 18.0247L19.4377 9.53827C20.3759 8.60052 20.9031 7.32831 20.9031 6.00183C20.9031 4.67534 20.376 3.40321 19.4378 2.46546C18.5001 1.52727 17.2278 1 15.9013 1Z"
                  fill="#414141" />
              </svg>

            </div>
          </div>

          <div class="product-info">
            <div class="price-row">
              <div>
                <h3>{{ product.price }}</h3>
                <p>С картой</p>
              </div>
              <div class="old-price" v-if="product.oldPrice">
                <span>{{ product.oldPrice }}</span>
                <p>Обычная</p>
              </div>
            </div>
            <div class="product-name">{{ product.name }}</div>
            <div class="rating"><svg width="256" height="16" viewBox="0 0 256 16" fill="none"
                xmlns="http://www.w3.org/2000/svg">
                <path
                  d="M7.10326 1.81698C7.47008 1.07374 8.52992 1.07374 8.89674 1.81699L10.1185 4.29249C10.2641 4.58763 10.5457 4.7922 10.8714 4.83953L13.6033 5.2365C14.4235 5.35568 14.751 6.36365 14.1575 6.94219L12.1807 8.8691C11.945 9.09884 11.8375 9.42984 11.8931 9.75423L12.3598 12.4751C12.4999 13.292 11.6424 13.9149 10.9088 13.5293L8.46534 12.2446C8.17402 12.0915 7.82598 12.0915 7.53466 12.2446L5.09119 13.5293C4.35756 13.9149 3.50013 13.292 3.64024 12.4751L4.1069 9.75423C4.16254 9.42984 4.05499 9.09884 3.81931 8.8691L1.8425 6.94219C1.24898 6.36365 1.57649 5.35568 2.39671 5.2365L5.12859 4.83953C5.4543 4.7922 5.73587 4.58763 5.88153 4.29249L7.10326 1.81698Z"
                  fill="#FF6633" />
                <path
                  d="M27.1033 1.81698C27.4701 1.07374 28.5299 1.07374 28.8967 1.81699L30.1185 4.29249C30.2641 4.58763 30.5457 4.7922 30.8714 4.83953L33.6033 5.2365C34.4235 5.35568 34.751 6.36365 34.1575 6.94219L32.1807 8.8691C31.945 9.09884 31.8375 9.42984 31.8931 9.75423L32.3598 12.4751C32.4999 13.292 31.6424 13.9149 30.9088 13.5293L28.4653 12.2446C28.174 12.0915 27.826 12.0915 27.5347 12.2446L25.0912 13.5293C24.3576 13.9149 23.5001 13.292 23.6402 12.4751L24.1069 9.75423C24.1625 9.42984 24.055 9.09884 23.8193 8.8691L21.8425 6.94219C21.249 6.36365 21.5765 5.35568 22.3967 5.2365L25.1286 4.83953C25.4543 4.7922 25.7359 4.58763 25.8815 4.29249L27.1033 1.81698Z"
                  fill="#FF6633" />
                <path
                  d="M47.1033 1.81698C47.4701 1.07374 48.5299 1.07374 48.8967 1.81699L50.1185 4.29249C50.2641 4.58763 50.5457 4.7922 50.8714 4.83953L53.6033 5.2365C54.4235 5.35568 54.751 6.36365 54.1575 6.94219L52.1807 8.8691C51.945 9.09884 51.8375 9.42984 51.8931 9.75423L52.3598 12.4751C52.4999 13.292 51.6424 13.9149 50.9088 13.5293L48.4653 12.2446C48.174 12.0915 47.826 12.0915 47.5347 12.2446L45.0912 13.5293C44.3576 13.9149 43.5001 13.292 43.6402 12.4751L44.1069 9.75423C44.1625 9.42984 44.055 9.09884 43.8193 8.8691L41.8425 6.94219C41.249 6.36365 41.5765 5.35568 42.3967 5.2365L45.1286 4.83953C45.4543 4.7922 45.7359 4.58763 45.8815 4.29249L47.1033 1.81698Z"
                  fill="#BFBFBF" />
                <path
                  d="M67.1033 1.81698C67.4701 1.07374 68.5299 1.07374 68.8967 1.81699L70.1185 4.29249C70.2641 4.58763 70.5457 4.7922 70.8714 4.83953L73.6033 5.2365C74.4235 5.35568 74.751 6.36365 74.1575 6.94219L72.1807 8.8691C71.945 9.09884 71.8375 9.42984 71.8931 9.75423L72.3598 12.4751C72.4999 13.292 71.6424 13.9149 70.9088 13.5293L68.4653 12.2446C68.174 12.0915 67.826 12.0915 67.5347 12.2446L65.0912 13.5293C64.3576 13.9149 63.5001 13.292 63.6402 12.4751L64.1069 9.75423C64.1625 9.42984 64.055 9.09884 63.8193 8.8691L61.8425 6.94219C61.249 6.36365 61.5765 5.35568 62.3967 5.2365L65.1286 4.83953C65.4543 4.7922 65.7359 4.58763 65.8815 4.29249L67.1033 1.81698Z"
                  fill="#BFBFBF" />
                <path
                  d="M87.1033 1.81698C87.4701 1.07374 88.5299 1.07374 88.8967 1.81699L90.1185 4.29249C90.2641 4.58763 90.5457 4.7922 90.8714 4.83953L93.6033 5.2365C94.4235 5.35568 94.751 6.36365 94.1575 6.94219L92.1807 8.8691C91.945 9.09884 91.8375 9.42984 91.8931 9.75423L92.3598 12.4751C92.4999 13.292 91.6424 13.9149 90.9088 13.5293L88.4653 12.2446C88.174 12.0915 87.826 12.0915 87.5347 12.2446L85.0912 13.5293C84.3576 13.9149 83.5001 13.292 83.6402 12.4751L84.1069 9.75423C84.1625 9.42984 84.055 9.09884 83.8193 8.8691L81.8425 6.94219C81.249 6.36365 81.5765 5.35568 82.3967 5.2365L85.1286 4.83953C85.4543 4.7922 85.7359 4.58763 85.8815 4.29249L87.1033 1.81698Z"
                  fill="#BFBFBF" />
              </svg>
            </div>
            <button :class="product.active ? 'active-btn' : 'default-btn'">В корзину</button>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped>
.card-wrapper {
  max-width: 1700px;
  margin: 0 auto;
  padding: 40px 0;
  background: #f9f4e8;
}

.products-section {
  margin-bottom: 70px;
  padding: 0 60px;
}

.section-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 32px;
}

.section-top h2 {
  font-size: 36px;
  color: #414141;
}

.all-link {
  display: flex;
  align-items: center;
  gap: 10px;
  color: #606060;
  cursor: pointer;
  font-size: 16px;
}

.products-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 32px;
}

.product-card {
  background: white;
  border-radius: 8px;
  overflow: hidden;
  transition: 0.2s;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.06);
}

.product-card:hover {
  transform: translateY(-4px);
}

.product-image {
  position: relative;
  height: 260px;
  overflow: hidden;
  background: white;
}

.product-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.sale {
  position: absolute;
  left: 10px;
  bottom: 10px;
  background: #ff6633;
  color: white;
  padding: 4px 8px;
  border-radius: 4px;
  font-size: 14px;
}

.heart {
  position: absolute;
  top: 10px;
  right: 10px;
  font-size: 22px;
  color: #c8c8c8;
  cursor: pointer;
}

.product-info {
  padding: 14px;
}

.price-row {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.price-row h3 {
  font-size: 22px;
  color: #414141;
}

.price-row p {
  font-size: 12px;
  color: #bfbfbf;
}

.old-price {
  text-align: right;
}

.old-price span {
  font-size: 16px;
  color: #8f8f8f;
}

.product-name {
  margin-top: 10px;
  min-height: 48px;
  font-size: 15px;
  color: #414141;
  line-height: 1.4;
}

.rating {
  margin-top: 12px;
  color: #ff6633;
  font-size: 14px;
}

.default-btn,
.active-btn {
  width: 100%;
  height: 40px;
  margin-top: 14px;
  border-radius: 6px;
  cursor: pointer;
  transition: 0.2s;
  font-size: 16px;
}

.default-btn {
  border: 1px solid #70C05B;
  background: white;
  color: #70C05B;
}

.default-btn:hover {
  background: #70C05B;
  color: white;
}

.active-btn {
  border: none;
  background: #ff6633;
  color: white;
}
</style>