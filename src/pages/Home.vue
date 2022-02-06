<template>
    <main>

        <div class="text-top">Videos novos toda <b>quinta</b> às <b>20h</b></div>

        <a href="https://youtube.com/wdevoficial" target="_blank" >
        <img alt="Inscreva-se" class="subscribe" src="https://raw.githubusercontent.com/william-costa/wdev-mock-site-resources/master/assets/images/subscribe.svg"></a>

        <div class="text-bottom">youtube.com/wdevoficial</div>

    </main>
</template>

<script>
export default {
    name: 'Home'
}
</script>

<style scoped>
    main{
        background-color: var(--color-background-home);
        justify-content: center;
        align-items: center;
    }

    .subscribe{
        width: 300px;
    }

    .text-top{
        margin-bottom: 20px;
        font-size: 22px;
        color: var(--color-text-light);
    }

    .text-bottom{
        margin-top: 20px;
        font-size: 22px;
        color: var(--color-text-light);
    }

    @media(min-width: 700px){
        .subscribe{
            width: 350px;
        }
    }
</style>