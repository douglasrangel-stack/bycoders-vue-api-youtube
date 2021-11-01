<template>
  <div class="history">
    <section class="list-view">
          <div class="container">
            <div class="row" v-if="selectVideo">
              <div class="col-md-8">
                  <div class="scrool-fixed">
                    <VideoPlay :video="selectVideo" />
                  </div>
              </div>
              <div class="col-md-4">
                  <VideoList :myVideos="videos" @videoSelect="onVideoSelect"/>
              </div>
            </div>
            <h1 class="not-found" v-else>Você não assitiu nenhum vídeo.</h1>
          </div>
      </section>
  </div>
</template>

<script>
import VideoList from '@/components/VideoList';
import VideoPlay from '@/components/VideoPlay';


export default {
  name: 'History',
   components: {
    VideoList,
    VideoPlay
  },
  data(){
    return {
      videos: [],
      selectVideo: null 
    };
  },
  methods:{
    onVideoSelect(video){
      this.selectVideo = video;
    }
  },
  mounted: function() {
        var getHistory = JSON.parse(localStorage.getItem("history"));
        if(getHistory) {
            this.videos = getHistory.reverse();
            this.selectVideo = getHistory[0];
        }
  },
}
</script>

<style lang="scss" scoped>
$black: #282828;
    .list-view {
      padding: 0 60px;
    }
    .scrool-fixed {
      position: sticky;
      top: 10px;
    }

    .not-found {
        font-size: 22px;
        line-height: 32px;
        color: $black;
        font-weight: bold;
        margin-top: 30px;
    }
</style>