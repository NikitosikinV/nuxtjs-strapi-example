<template>
  <div class="app">
    <h1>Контакты</h1>
    <p><b>Почта:</b> {{ email }}</p>
    <p><b>Телефон:</b> {{ tel }}</p>
    <p>
      <a :href="insta">Instagram</a>
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
      tel: null,
      insta: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.contacts = await this.$strapi.$contacts.find();
      this.email = this.contacts[0].email;
      this.tel = this.contacts[0].tel;
      this.insta = this.contacts[0].insta;
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
