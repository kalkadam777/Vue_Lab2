<script setup>
import { ref } from 'vue'

defineProps({
  msg: String,
})

const count = ref(0)
</script>

<template>
  <div class="container_menu">
    <div class="menu_text">MENU</div>
    <div class="list_menu">
      <div class="blog_text">ADVENTURE BLOG</div>
      <div class="blog_text">NATURE BLOG</div>
      <div class="blog_text">FASHION BLOG</div>
      <div class="blog_text">MODERN BLOG</div>
      <div class="contact_data">
        <div class="contacts_text">CONTACTS</div>
        <div class="list_text">
          <p class="mini_text">PHONE: +1(234)-23-45-22</p>
          <p class="mini_text">ADDRESS: Green st., Yalow park</p>
          <p class="mini_text">EMAIL: Yallow@park.info</p>
        </div>
      </div>
    </div>
  </div>
  
</template>

<style >
@import url('https://fonts.googleapis.com/css2?family=Inknut+Antiqua&family=Jersey+15&display=swap');
  .container_menu {
    background: #C1EBF1;
    width: 410px;
    height: 100vh;
    padding: 10px 20px 17px 20px;
  }

  .container_menu {
    display: flex;
    flex-direction: column;
    /* justify-content: center; */
    align-items: center;
  }

  .menu_text {
    text-align: center;
    color: #615C5C;
    font-family: "Jersey 15";
    font-size: 46px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    border-radius: 10px;
    background: #FFF;
    width: 380px;
    margin-bottom: 40px;
    padding: 5px 0px 5px 0px;
  }

  .list_menu {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 35px;
    border-radius: 12px;
    background: #FFF;
    padding: 25px 0 20px 0px;
  }

  .blog_text {
    color: #FFF;
    font-family: "Jersey 15";
    font-size: 46px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
    background: linear-gradient(90deg, #4CD87C 0%, #42D669 63.42%, #3DD55E 100%);
    text-align: center;
    width: 380px;
    padding-top: 10px;
    padding-bottom: 10px;

  }

  .contact_data {
    margin-top: 85px;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
    border-radius: 10px;
    background: linear-gradient(180deg, #AFF090 0%, #45C330 100%);
    width: 320px;
    padding: 10px 0px 20px 18px;
  }

  .contacts_text {
    text-align: center;
    color: #FFF;
    font-family: "Jersey 15";
    font-size: 46px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
  }

  .list_text {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }
  .mini_text {
    color: #FFF;
    font-family: "Jersey 15";
    font-size: 32px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
  }
</style>
