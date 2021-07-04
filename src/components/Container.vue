<template>
     <div v-for="(a,i) in feedData" :key="a">
        <Post :feedData="feedData[i]"/>
    </div>
</template>

<script>
import Post from './Post.vue';

export default {
    
    data() {
        return {
            
        }
    },

    components: {
        Post : Post
    }
    ,
    props : {
        //feedData : Array 이름 : 종류
        feedData : Array,
    }

}
</script>

<style>

</style>