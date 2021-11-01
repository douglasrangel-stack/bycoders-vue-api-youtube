<template>
    <li class="list-group-item" @click="onVideoSelect()">
        <img :src="thumbnailUrl">
        <p class="media-title">{{title}}</p>
    </li>
</template>
<script>
export default {
    name:'VideoListItem',
    props:['video'],
    computed:{
        thumbnailUrl (){
            return this.video.snippet.thumbnails.default.url;
        },
        title(){
           return this.video.snippet.title;
        }
    },
    methods: {
        onVideoSelect(){
            if (/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
                window.scrollTo({
                    top: 0,
                    behavior: "smooth",
                });
            }
            
            this.$emit('videoSelect',this.video);
            var history = [];
            var getHistory = JSON.parse(localStorage.getItem("history"));

            if(getHistory) {
                history = JSON.parse(localStorage.getItem("history"));
            }

        
            if(history.length == 0) {
                 history.push(this.video);    
            }
            

            var item = this.video.etag;
            var count = 0;

           
            history.forEach((e) => {
                if(e.etag === item) {
                    count++;
                }
            });

            if(count  === 0) {
                history.push(this.video);
            }
            
            localStorage.setItem("history", JSON.stringify(history));
        }
    },
}
</script>

<style lang="scss" scoped>

$red: #ff0000;
$black: #282828;
.list-group-item {
    list-style: none;
    margin-bottom: 10px;
    padding-bottom: 10px;
    border-bottom: 1px solid #ececec;
    display: flex;
    align-items: flex-start;
    cursor: pointer;
    img {
        margin-right: 10px;
    }
    .media-title {
        font-size: 16px;
        line-height: 22px;
        font-weight: bold;
        color: $black;
    }
    &:last-child {
        border-bottom: none;
    }
}
</style>