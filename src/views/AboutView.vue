<template>
  <div class="header_nav">
      <div class="nav_logo">
        <a href="https://uk.wikipedia.org/wiki/%D0%A0%D1%96%D0%BA_%D1%82%D0%B0_%D0%9C%D0%BE%D1%80%D1%82%D1%96"><img class="logo_img" src="../assets/image/logo-2.webp" alt="#"></a> <!-- Navigation    -->
      </div>
      <div>
        <ul class="nav_list_pages" >
          <li><a href="#">Пошук героя</a></li>
          <li><a href="https://www.youtube.com/watch?v=5dvPIdBNbEI&ab_channel=A.K.">Міжгалактичне ТВ</a></li>
          <li><a href="https://rozetka.com.ua/search/?text=%D1%80%D1%96%D0%BA+%D1%96+%D0%BC%D0%BE%D1%80%D1%82%D1%96">Речі на пам'ять</a></li>
        </ul>
      </div>
      <div>
        <ul class="nav_list_soc" >
          <li><a href="https://www.instagram.com/rickandmorty/"><img src="../assets/image/instagram-icon.svg" alt=""></a></li>
          <li><a href="https://telegram.me/s/Rik_i_Morti2"><img src="../assets/image/telegram-icon.svg" alt=""></a></li>
          <li><a href="https://www.facebook.com/people/%D0%A0%D0%B8%D0%BA-%D0%B8-%D0%9C%D0%BE%D1%80%D1%82%D0%B8/100069787462769/"><img src="../assets/image/facebook-icon.svg" alt=""></a></li>
        </ul>
      </div>
  </div>
</template>

<script>

</script>

<style scoped lang="scss">
.header_nav {
  width: 100%;
  height: 100%;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  align-items: center;
  background-image:inherit

}
.logo_img {
  width: 100%;
  max-width: 60px;
  
}

ul,
li {
  margin: 0;
  padding: 0;
  list-style: none;
}
.nav_list_pages {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  gap: 20px;
  text-transform: uppercase;
}

.nav_list_soc {
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  gap: 10px;
}
</style>