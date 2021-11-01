<template>
    <ul class="list-group">
        <VideoListItem v-for="video in myVideos" :video ="video" :key="video.etag" @videoSelect="onVideoSelect"  />
    </ul>
</template>

<script>
import VideoListItem from '@/components/VideoListItem';
export default {
    name:'VideoList',
    components:{
        VideoListItem,
    },
    props:['myVideos'],
    methods: {
        onVideoSelect(video){
            this.$emit('videoSelect',video);
        }
    },
}
</script>