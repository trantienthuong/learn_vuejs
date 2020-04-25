<template>
  <v-layout>
    <div>
      <h1>Videos</h1>
      <div class="video-container">
        <div v-for="video in $store.state.videos" :key="video.name">
          <div class="video-box">
            <img :src="video.thumbnail" />
            <div>
              <h3>{{ video.name }}</h3>
              <nuxt-link :to="`/videos/${video.id}`">{{video.name}}</nuxt-link>
              <div v-html="video.description"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </v-layout>
</template>

<script>
import axios from "axios";
export default {
  // async asyncData({$axios}) {
  //   let response = await $axios.get('/videos')
  //   //data có thể lấy từ server hoặc fake 1 file Json
  //   let videos = response.data.data.map(v => v.attributes);
  //   return {
  //     videos
  //   }
  // },
  async fetch({ $axios, store }) {
    let response = await $axios.get("/videos");
    let videos = response.data.data.map(v => v.attributes);
    store.commit("SET_VIDEOS", videos);
  }
  // data() {
  //   return {
  //     videos: []
  //   };
  // },
  // async created() {
  //   try {
  //     const response = await axios.get(`http://localhost:3000/videos`);
  //     this.videos = response.data;
  //   }catch(e){
  //     console.log('tag', 'e')
  //   }
  // }
};
</script>
<style scoped lang="scss">
.video-container {
  .video-box {
    border: 1px solid black;
    border-radius: 10px;
    margin: 10px;
    padding: 10px;
    text-align: left;
    display: flex;
    justify-content: flex-start;
    img {
      width: 200px;
      padding: 10px;
    }
  }
}
</style>