<template>
  <div class="app">
    <h1>Главная страница</h1>
    <img
      :src="img"
      alt="портрет"
    />
    <h2>{{ name }}</h2>
    <hr />
    <nuxt-link to="/about">обо мне</nuxt-link>
    <nuxt-link to="/contacts">контакты</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      img: null,
      name: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.mains = await this.$strapi.$mains.find();
      this.img = this.mains[0].photo;
      this.name = this.mains[0].name;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>

<style scoped>
img {
  height: 50vh;
}
</style>
