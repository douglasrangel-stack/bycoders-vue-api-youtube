<template>
  <div class="home">
      <section class="list-view">
          <div class="container">
            <SearchVideo @termChange="onTermChange" />
            <div class="row">
              <div class="col-md-8">
                  <div class="scrool-fixed">
                    <VideoPlay :video="selectVideo" />
                  </div>
              </div>
              <div class="col-md-4">
                  <VideoList :myVideos="videos" @videoSelect="onVideoSelect"/>
              </div>
            </div>
          </div>
      </section>
  </div>
</template>

<script>
import SearchVideo from '@/components/SearchVideo';
import VideoList from '@/components/VideoList';
import VideoPlay from '@/components/VideoPlay';
import axios from 'axios';

const API_KEY = 'AIzaSyBqbj5ayrlc-vss0l5y_2YiImha_7oRgy8';

export default {
  name: 'Videos',
   components: {
    SearchVideo,
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
    onTermChange(searchTerm){
         axios.get('https://www.googleapis.com/youtube/v3/search',{
       params:{
         key: API_KEY,
         type:'video',
         maxResults: '30',
         resultsPerPage: '30',
         part:'snippet',
         q:searchTerm
       }
         }).then(response => {
           this.videos = response.data.items;
           this.selectVideo = response.data.items[0];
         });
    },
    onVideoSelect(video){
      this.selectVideo = video;
    }
  },
  mounted: function() {
    axios.get('https://www.googleapis.com/youtube/v3/search',{
      params:{
        key: API_KEY,
        type:'video',
        maxResults: '30',
        resultsPerPage: '30',
        part:'snippet',
        q:'bycoders'
      }
      }).then(response => {
        this.videos = response.data.items;
        this.selectVideo = response.data.items[0];
      });
  },
}
</script>

<style lang="scss" scoped>
    .list-view {
      padding: 0 60px;
    }
    .scrool-fixed {
      position: sticky;
      top: 10px;
    }
</style>