<template>

  <div>

    <div class="header">
      <ul class="header-button-left">
        <li>Cancel</li>
      </ul>
      <ul class="header-button-right">
        <li>Next</li>
      </ul>
      <img src="./assets/logo.png" class="logo" />
    </div>

    <Container :feedData="feedData" />

    <div class="footer">
      <ul class="footer-button-plus">
        <input type="file" id="file" class="inputfile" />
        <label for="file" class="input-plus">+</label>
      </ul>
    </div>
  </div>
</template>

<script>
import Container from './components/Container.vue';
import feedDatd from './assets/js/feedData.js';



export default {
  name: "App",
  data() {
    return {
      feedData : feedDatd,
    }
  },
  components: {
    Container
  },
};
</script>

<style>
  @import url(./assets/css/app.css);
</style>
