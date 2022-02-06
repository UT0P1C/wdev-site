<template>

    <main>

        <section class="container">

            <h1>Vídeos</h1>

            <section class="videos">
                
                <div class="video" v-for="(video, index) in videos" :key="index" target="_blank">

                    <a :href="video.link">

                        <img  :src="video.thumb" :alt="video.title" >

                        <div class="video-title">{{video.title}}</div>

                    </a>

                </div>

            </section>

        </section>

    </main>

</template>

<script>

import api from '@/services/api.js'

export default {
    name: 'Videos',
    data(){
        return{
            videos: []
        }
    },
    mounted(){
        api.get('https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/videos.json').then(response => {
            this.videos = response.data;
        });
    }
}
</script>

<style scoped>
    main {
        align-items: center;
    }

    .videos{
        display: flex;
        flex-direction: column;
        align-items: center;

    }

    .video{
        width: 80%;
        margin-bottom: 20px;
    }

    .video a {
        color: var(--color-text-dark);
        font-weight: 600;
        text-align: center;
    }

    .video img{
        width: 100%;
    }

    @media (min-width: 700px){
        .videos{
            flex-direction: row;
            align-items: flex-start;
            flex-wrap: wrap;
        }

        .video {
            margin-right: 30px;
            width: 300px;
        }
    }

</style>