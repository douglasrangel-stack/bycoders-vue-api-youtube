<template>
  <div v-if="video">
    <div class="boxvideo">
        <iframe  :src="videoUrl" allow="autoplay" />
    </div>
    <h4 class="boxvideo-title">
        {{video.snippet.title}}
    </h4>
    <p class="boxvideo-description">
        {{video.snippet.description}}
    </p>
  </div>
</template>

<script>
export default {
    name:'VideoPlay',
    props:[
        'video'
    ],
    computed:{
        videoUrl(){
            const videoId = this.video.id.videoId;
            return `https://www.youtube.com/embed/${videoId}?autoplay=1&controls=0`;
        }
    }
}
</script>

<style lang="scss" scoped>

$red: #ff0000;
$black: #282828;

.boxvideo {
    position: relative;
    padding-bottom: 56.25%;
    padding-top: 25px;
    height: 0;
    margin: 0 auto 20px;
}

.boxvideo iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}

.boxvideo-title {
    font-size: 22px;
    line-height: 32px;
    color: $black;
    font-weight: bold;
}
.boxvideo-description {
    font-size: 15px;
    line-height: 22px;
    font-weight: 400;
    color: $black;
    margin-top: 5px;
    margin-bottom: 30px;
}
</style>