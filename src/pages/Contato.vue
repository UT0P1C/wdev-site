<template>

    <main>

        <section class="container">

            <h1>Contato</h1>

            <div class="contact"></div>

        </section>

    </main>

</template>

<script>

import api from '@/services/api.js'

export default {
    name: 'Contato',
    data(){
        return{
            contacts: []
        }
    },
    mounted(){
        api.get('https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/api/contacts.json').then(response => {
            this.contacts = response.data;
        });
    }
}
</script>

<style scoped>

    main {
        align-items: center;
    }

</style>