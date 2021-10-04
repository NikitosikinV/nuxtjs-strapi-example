<template>
  <div class="app">
    <h1>Контакты</h1>
    <p><b>Почта:</b> {{ email }}</p>
    <p><b>Телефон:</b> +7963752----</p>
    <p>
      <a href="https://www.instagram.com/nikitosikinv/">Instagram</a>
    </p>
    <hr />
    <nuxt-link to="/">главная</nuxt-link>
    <nuxt-link to="/about">обо мне</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.contacts = await this.$strapi.$contacts.find();
      this.email = this.contacts[0].email;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>

<style scoped>
hr {
  margin-top: 5vh;
}
</style>
