<template>
  <div class="app">
    <h1>Обо мне</h1>
    <div class="main">
      <p><b>ФИО:</b> {{ fio }}</p>
      <p><b>Дата рождения:</b> {{ birthDate }}</p>
      <p><b>Город:</b> {{ city }}</p>
    </div>
    <div class="education">
      <p><b>Место учебы:</b> {{ education }}</p>
      <p><b>Специальность:</b> {{ species }}</p>
    </div>
    <div class="work">
      <p><b>Компания:</b> {{ company }}</p>
      <p><b>Должность:</b> {{ position }}</p>
    </div>
    <div class="extra">
      <p>
        <b>Хобби:</b> {{ hobby }}</p>
    </div>
    <hr />
    <nuxt-link to="/">главная</nuxt-link>
    <nuxt-link to="/contacts">контакты</nuxt-link>
  </div>
</template>

<script>
export default {
  data() {
    return {
      fio: null,
      birthDate: null,
      city: null,
      education: null,
      species: null,
      company: null,
      position: null,
      hobby: null,
      error: null
    };
  },
  async mounted() {
    try {
      this.abouts = await this.$strapi.$abouts.find();
      this.fio = this.abouts[0].FIO;
      this.birthDate = this.abouts[0].birthDate;
      this.city = this.abouts[0].city;
      this.education = this.abouts[0].education;
      this.species = this.abouts[0].species;
      this.company = this.abouts[0].company;
      this.position = this.abouts[0].position;
      this.hobby = this.abouts[0].hobby;
    } catch (error) {
      this.error = error;
      console.log(this.error);
    }
  }
};
</script>

<style scoped>
.app div {
  margin-bottom: 5vh;
}

.app div:after {
  content: "---";
}
</style>
