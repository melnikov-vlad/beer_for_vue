<template>
  <div>
    <div class="header_nav">
      <div class="nav_logo">
        <a href="https://uk.wikipedia.org/wiki/%D0%A0%D1%96%D0%BA_%D1%82%D0%B0_%D0%9C%D0%BE%D1%80%D1%82%D1%96"><img
            class="logo_img" src="../assets/image/favicon.png" alt="#"></a> <!-- Navigation    -->
      </div>
      <div>
        <ul class="nav_list_pages">
          <li><a href="#">Пошук героя</a></li>
          <li><a href="https://www.youtube.com/watch?v=5dvPIdBNbEI&ab_channel=A.K.">Міжгалактичне ТВ</a></li>
          <li><a href="https://rozetka.com.ua/search/?text=%D1%80%D1%96%D0%BA+%D1%96+%D0%BC%D0%BE%D1%80%D1%82%D1%96">Речі на
              пам'ять</a></li>
        </ul>
      </div>
      <div>
        <ul class="nav_list_soc">
          <li>
            <a href="https://www.instagram.com/rickandmorty/">
              <img class="nav_soc_img" src="../assets/image/instagram-icon.svg" alt=""></a>
          </li>
          <li>
            <a href="https://telegram.me/s/Rik_i_Morti2">
              <img class="nav_soc_img" src="../assets/image/telegram-icon.svg" alt=""></a>
          </li>
          <li><a href="https://www.facebook.com/people/%D0%A0%D0%B8%D0%BA-%D0%B8-%D0%9C%D0%BE%D1%80%D1%82%D0%B8/100069787462769/">
              <img class="nav_soc_img" src="../assets/image/facebook-icon.svg" alt=""></a>
          </li>
        </ul>
      </div>
    </div>
    <div class="main_wrapper">
      <div>
        <h1 class="hero_text">Великий світ Ріка та Морті</h1>
      </div>
      <label for="search">
        <div>
          <h2 class="hero_task_text">Давай число від 1 до 826 і подивимося який персонаж тобі випаде</h2>
        </div>
        <input v-model="numberPerson" class="inp_search" type="text" name="findphrases" id="search"
          placeholder="Вводи число">
      </label>
      <br>
      <button class="btn_search" @click="searchNumberPerson">Почнемо пошук</button>
      <!-- <button class="btn_search" @click="">Випадкова персонаж</button> -->
      <!-- if we have single person -->
      <div class="main_img" v-if="persone.name">
        <img class="img_found" :src="persone.image" :alt="persone.name">
        <ul class="img_info_found">
          <li>
            <h3>Ім'я: {{ persone.name }}</h3>
          </li>
          <li>
            <h4>Стать: {{ persone.gender }}</h4>
          </li>
          <li>
            <h5>Життєвий статус: {{ persone.status }}</h5>
          </li>
        </ul>
    
      </div>
      <!-- if we have a list of the persones -->
      <div v-if="persones.length && !persone.name" v-for="onePers in persones" :key="persones.id">
        <img :src="onePers.image" :alt="onePers.name">
        <h3>{{ onePers.name }}</h3>
      </div>
      <!-- <div>
                <img :src="persones.image" :alt="persones.name">
                <h3>{{ persones.name }}</h3>
            </div> -->
    </div>
  </div>
</template>

<script>
const URL = 'https://rickandmortyapi.com/api/character/';
export default {
  name: 'bad_page',
  components: {
  },
  props: {
    msg: String
  },
  data() {
    return {
      persones: [],
      persone: {},
      numberPerson: '',

    }
  },
  props: {
    type: String,
    default: '',
  },
  async mounted() {
    // this.searchAllPerson();
  },
  methods: {
    async searchNumberPerson() {
      const res = await fetch(URL + this.numberPerson);
      const persone = await res.json();
      this.persone = persone;
    },
    async searchAllPerson() {
      const res = await fetch(URL);
      const persones = await res.json();
      this.persones = persones.results;
    },
    // async randomNumber() {
    //   min = Math.ceil(1);
    //   max = Math.floor(826);
    //   return Math.floor(Math.random() * (max - min + 1) + min);
    //   console.log(min);
    // },
    // async randomSearch() {
    //   const res = await fetch(URL + randomNumber());
    //   const persone = await res.json();
    //   this.persone = persone;
    // }
  }
}
</script>

<style scoped lang="scss" src="../assets/styles/index.scss">
</style>