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

    <div class="moreFeed">
      <button @click="more">더보기</button>
    </div>



    <div class="footer">
      <ul class="footer-button-plus">
        <input type="file" id="file" class="inputfile" />
        <label for="file" class="input-plus">+</label>
      </ul>
    </div>
  </div>

  <!-- <div v-if="step == 0">내용0</div>
  <div v-if="step == 1">내용1</div>
  <div v-if="step == 2">내용2</div>
  
  
  <button @click="step = 0">버튼0</button>
  <button @click="step = 1">버튼1</button>
  <button @click="step = 2">버튼2</button> -->
  

</template>

<script>
import Container from './components/Container.vue';
import feedData from './assets/js/feedData.js';
import axios from 'axios';



export default {
  name: "App",
  data() {
    return {
      step : 1,
      feed1 : false,
      feedData : feedData,
      morePointer : 0,
    }
  },
  components: {
    Container
  },

  mounted(){
    this.emitter.on('작명', (a)=>{
      console.log(a)
    })
  },
  methods : {
    
    publish(){
      var myfeed = {

        name: "Kim Hyun",
        userImage: "https://placeimg.com/100/100/arch",
        postImage: this.postImage,
        likes: 36,
        date: "May 15",
        liked: false,
        content: this.feedData,
        filter: "perpetua"

      }
    },
    more(){
      
      // axios.post('https://codingapple1.github.io/vue/more0.json')
      // .then()
      // .catch((err)=>{
      //   console.log(err)
      // });
      
      axios.get(`https://codingapple1.github.io/vue/more`+`${this.morePointer}`+`.json`)
      .then( moreData =>{
        console.log(moreData.data);
        this.morePointer++;
        console.log(this.morePointer);
        this.feedData.push(moreData.data);
      })
    }
  }
};
</script>

<style>
  @import url(./assets/css/app.css);
</style>
