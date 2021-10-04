<template>
  <div class="app">
    <h1>Обо мне</h1>
    <div class="main">
      <p><b>ФИО:</b> Воробьев Никита Евгеньевич</p>
      <p><b>Дата рождения:</b> 09.04.2001</p>
      <p><b>Город:</b> Москва</p>
    </div>
    <div class="education">
      <p><b>Место учебы:</b> МТКП МГТУ им. Н.Э. Баумана</p>
      <p><b>Специальность:</b> прикладная информатика</p>
    </div>
    <div class="work">
      <p><b>Компания:</b> Affinage</p>
      <p><b>Должность:</b> стажер фронтендер</p>
    </div>
    <div class="extra">
      <p>
        <b>Хобби:</b> компьютерные игры, книги, спорт, чай, фото, видео, кино,
        вино, настольные игры
      </p>
    </div>
    <hr />
    <nuxt-link to="/">главная</nuxt-link>
    <nuxt-link to="/contacts">контакты</nuxt-link>
  </div>
</template>

<style scoped>
.app div {
  margin-bottom: 5vh;
}

.app div:after {
  content: "---";
}
</style>
