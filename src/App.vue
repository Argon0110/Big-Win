<script setup>
import { ref } from "vue";
import Main from "./components/Main.vue";

const Image = ref(0);

setInterval(() => Image.value = Image.value < 3 ? Image.value + 1 : 0, 5000);
</script>

<template>
  <div id="mainWrapper">
    <article>
      <img v-if="Image === 0" class="BannerImg" src="/src/assets/AdTop2.png"/>
      <img v-else-if="Image === 1" class="BannerImg" src="/src/assets/AdTop1.png"/>
      <img v-else-if="Image === 2" class="BannerImg" src="/src/assets/GOAT.png"/>
      <img v-else-if="Image === 3" class="BannerImg" src="/src/assets/Ouch.png"/>
    </article>
    <Main />
    <article>
      <img v-if="Image % 2 === 0" class="BannerImg" src="/src/assets/CurlyHair.png"/>
      <img v-else class="BannerImg" src="/src/assets/Sardo.png"/>
    </article>
  </div>
</template>

<style scoped>
  #mainWrapper {
    height: calc(100vh - 60px);
  }
  article {
    height: 20%;
  }
  main {
    height: 60%;
  }
  .BannerImg {
    width: 100%;
    height: 100%;
    object-fit: contain;
  }
</style>
