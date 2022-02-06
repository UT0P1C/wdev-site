<template>
    
    <header>
    
        <nav class="container">
            <a href="/"> <img src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" alt="WDEV" id="logo"></a>

            <img src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/menu.svg" alt="abrir menu" id="menu-button" v-on:click="openMenu">

            <div id="menu-overlay" v-if="menuActive" v-on:click="closeMenu"></div>

            <div id="menu-items" :class="{active:menuActive}">

                <img src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/wdev.svg" alt="WDEV" id="menu-logo">

                <ul>

                    <li><a href="/">Home</a></li>
                    <li><a href="/videos">Videos</a></li>
                    <li><a href="/Sobre">Sobre</a></li>
                    <li><a href="/Contato">Contato</a></li>

                </ul>

            </div>

        </nav>
    
    </header>

</template>

<script>
export default {
    name: 'Header',
    data(){
        return{
            menuActive: false
        }
    },
    methods: {
        openMenu: function(){
            this.menuActive = true;
        },
        closeMenu: function(){
            this.menuActive = false;
        }
    }
}
</script>
<style scoped>

    header{
        background-color: var(--color-background-nav);
        width: 100%;
        height: 60px;
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #logo{
        width: 130px;

    }
    #menu-button{
        width: 30px;
    }

    nav{
        display: flex;
        justify-content: space-between;
        align-items: center;
        height: 60px;
    }

    #menu-overlay{
        position: fixed;
        top: 0;
        left: 0;
        width: 40%;
        height: 100vh;
        background-color: black;
        opacity: 0.7;
    }

    #menu-logo{
        width: 110px;
        margin-top: 30px;
    }

    #menu-items{
        position: fixed;
        top: 0;
        right: 0;
        background-color: var(--color-background-nav);
        width: 60%;
        height: 100vh;
        display: none;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
    }

    #menu-items.active{
        display: flex;
    }

    ul {
        list-style: none;
        text-align: center;
    }
    
    ul li {
        margin: 20px 0px;
    }

    ul li a {
        color: var(--color-text-light);
    }

    @media(min-width: 700px){
        #menu-button,
        #menu-logo,
        #menu-overlay{
            display: none;
        }

        #menu-items{
            display: flex;
            position: static;
            width: auto;
            height: 60px;
        }

        ul{
            display: flex;
            height: 60px;
            align-items: center;
        }

        ul li {
            margin: 0;
            margin-left: 20px;
        }

    }
</style>