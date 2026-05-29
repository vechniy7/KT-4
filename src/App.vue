<script setup>
import CardBlock from './components/CardBlock.vue'
import SpecPredlojeniya from './components/SpecPredlojeniya.vue'
import NashiMagaz from './components/NashiMagaz.vue'
import State from './components/State.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <header>
    <div class="header-container">
      <div class="left-block">
        <img src="/logo.png" class="header-logo" alt="header-logo" />

        <button class="btn-catalog">
          <span class="stripes">
            <span class="stripe"></span>
            <span class="stripe"></span>
            <span class="stripe"></span>
          </span>
          Каталог
        </button>

        <div class="search-box">
          <input type="text" placeholder="Найти товар" />
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M2.5 10.5C2.5 6.08172 6.08172 2.5 10.5 2.5C14.9183 2.5 18.5 6.08172 18.5 10.5C18.5 14.9183 14.9183 18.5 10.5 18.5C6.08172 18.5 2.5 14.9183 2.5 10.5ZM10.5 3.5C6.63401 3.5 3.5 6.63401 3.5 10.5C3.5 14.366 6.63401 17.5 10.5 17.5C14.366 17.5 17.5 14.366 17.5 10.5C17.5 6.63401 14.366 3.5 10.5 3.5Z"
              fill="#414141" />
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M15.4463 15.4464C15.6415 15.2512 15.9581 15.2512 16.1534 15.4464L21.3534 20.6464C21.5486 20.8417 21.5486 21.1583 21.3534 21.3535C21.1581 21.5488 20.8415 21.5488 20.6463 21.3535L15.4463 16.1535C15.251 15.9583 15.251 15.6417 15.4463 15.4464Z"
              fill="#414141" />
          </svg>
        </div>
      </div>

      <div class="right-block">
        <div class="nav-item">
          <img src="/cerdce.png" alt="">
          <p>Избранное</p>
        </div>

        <div class="nav-item">
          <img src="/zakazy.png" alt="">
          <p>Заказы</p>
        </div>

        <div class="nav-item cart">
          <img src="/karzina.png" alt="">
          <p>Корзина</p>
        </div>

        <div class="profile">
          <img src="/avatar.png" alt="avatar" />
          <span>Алексей</span>
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path fill-rule="evenodd" clip-rule="evenodd"
              d="M5.64645 8.64645C5.84171 8.45118 6.15829 8.45118 6.35355 8.64645L12 14.2929L17.6464 8.64645C17.8417 8.45118 18.1583 8.45118 18.3536 8.64645C18.5488 8.84171 18.5488 9.15829 18.3536 9.35355L12.3536 15.3536C12.1583 15.5488 11.8417 15.5488 11.6464 15.3536L5.64645 9.35355C5.45118 9.15829 5.45118 8.84171 5.64645 8.64645Z"
              fill="#414141" />
          </svg>
        </div>
      </div>
    </div>
  </header>

  <img class="bg" src="/bg.jpg" alt="" />

  <main>
    <CardBlock />
    <SpecPredlojeniya />
    <NashiMagaz />
    <State />
    <Footer />
  </main>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  background: rgb(252, 255, 255);
  height: 72px;
  border-bottom: 1px solid #f3f3f3;
}

.header-container {
  width: 100%;
  height: 100%;
  padding: 0 60px;
  display: flex;
  align-items: center;
  justify-content: space-around;
}

.left-block {
  display: flex;
  align-items: center;
  gap: 24px;
}

.header-logo {
  width: 180px;
}

.btn-catalog {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  width: 140px;
  height: 40px;
  background-color: #70C05B;
  border: none;
  border-radius: 6px;
  color: white;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
  transition: 0.2s ease;
}

.btn-catalog:hover {
  background-color: #4d9a3a;
}

.stripes {
  display: flex;
  flex-direction: column;
  gap: 3px;
}

.stripe {
  width: 18px;
  height: 2px;
  background-color: white;
  border-radius: 2px;
}

.search-box {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 420px;
  height: 40px;
  padding: 0 14px;
  border: 1px solid #70C05B;
  border-radius: 6px;
}

.search-box input {
  width: 100%;
  border: none;
  outline: none;
  font-size: 14px;
}

.right-block {
  display: flex;
  align-items: center;
  gap: 30px;
}

.nav-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  cursor: pointer;
  color: #414141;
  font-size: 12px;
}

.nav-item img {
  margin-bottom: 4px;
  max-width: 24px;
}

.profile {
  display: flex;
  align-items: center;
  gap: 10px;
  cursor: pointer;
}

.profile img {
  width: 36px;
  height: 36px;
  border-radius: 50%;
  object-fit: cover;
}

.profile span {
  font-size: 14px;
  color: #414141;
}

.bg {
  width: 100%;
  margin-top: 5px;
}
</style>