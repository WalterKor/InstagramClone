<template>
  <div>
    <Post :feedData[0]= "feedData"/>
    <Post/>
    <Post/>
</div>
</template>

<script>
import Post from './Post.vue';

export default {
  components : {
    Post
  },
  props : {
    feedData : Array
  }
}
</script>

<style>

</style>