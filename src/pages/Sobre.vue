<template>

    <main>

        <section class="container">

            <h1>Vídeos</h1>

            <div class="about" v-html="about"></div>

        </section>

    </main>

</template>

<script>

import api from '@/services/api.js'

export default {
    name: 'Sobre',
    data(){
        return{
            about: ''
        }
    },
    mounted(){
        api.get('https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/about.json').then(response => {
            this.about = response.data.about;
        });
    }
}
</script>

<style scoped>

    main {
        align-items: center;
    }

    .about{
        margin-bottom: 40px;
        color: var(--color-text-dark);
    }

</style>