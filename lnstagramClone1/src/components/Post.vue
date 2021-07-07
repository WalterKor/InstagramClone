<template>
  <!-- 포스트 게시물 -->
  <div class="post">
    <div class="post-header">
      <div class="profile" :style="{ backgroundImage: `url(${feedData.userImage})` }"></div>
      <span class="profile-name">
        {{ feedData.name }}
        <!-- <slot></slot> -->
        </span>
    </div>
    <div class="post-body" :style="{ backgroundImage: `url(${feedData.postImage})` }"></div>
    <div class="post-content">
      <!-- 좋아요갯수 -->
      <p>{{ feedData.likes }}</p>
      <p>
        <strong>{{ feedData.name }}</strong>{{ feedData.content }}
      </p>
      <!-- 날짜 -->
      <p class="date">{{ feedData.date }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    feedData: Object,
    step: Number,
  },
};
</script>

<style>
.post {
  width: 100%;
}
.profile {
  background-image: url("https://placeimg.com/100/100/arch");
  width: 30px;
  height: 30px;
  background-size: 100%;
  border-radius: 50%;
  float: left;
}
.profile-name {
  display: block;
  float: left;
  padding-left: 10px;
  padding-top: 7px;
  font-size: 14px;
}
.post-header {
  height: 30px;
  padding: 10px;
}
.post-body {
  background-image: url("https://placeimg.com/640/480/animals");
  height: 450px;
  background-position: center;
  background-size: cover;
}
.post-content {
  padding-left: 15px;
  padding-right: 15px;
  font-size: 14px;
}
.date {
  font-size: 11px;
  color: grey;
  margin-top: -8px;
}
</style>
