<template>
  <div class="app">
    <h1>Главная страница</h1>
    <img
      src="https://sun9-1.userapi.com/impg/KHFQizP4dW7qcaV9PgQ5hghz9zgjJDjGwWtIxQ/yoVnHrmNq1c.jpg?size=2560x1616&quality=96&sign=930294cf4238244e71d25519f74216aa&type=album"
      alt="портрет"
    />
    <h2>Воробьев Никита</h2>
    <hr />
    <nuxt-link to="/about">обо мне</nuxt-link>
    <nuxt-link to="/contacts">контакты</nuxt-link>
  </div>
</template>

<style scoped>
img {
  height: 50vh;
}
</style>
