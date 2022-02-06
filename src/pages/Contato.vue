<template>

    <main>

        <section class="container">

            <h1>Contato</h1>

            <section class="contacts" >

                <div class="contact" v-for="(contact, index) in contacts" :key="index">

                    <div class="contact-title">

                        <p><b>{{contact.title}}</b></p>

                    </div>

                    <a :href="contact.link" target="_blank">{{contact.label}}</a>

                </div>
                
            </section>

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

    .contacts{
        margin-bottom: 40px;
        color: var(--color-text-dark);
    }

    .contact-title{
        font-weight: 600px;
        font-size: 18px;
        color: var(--color-text-dark);
    }

    .contact a{
        color: var(--color-text-dark);
    }

    .contact{
        margin-bottom: 20px;
    }

</style>