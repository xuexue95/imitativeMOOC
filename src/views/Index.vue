<template>
    <div class="index">
        <NewComer/>
        <TopBar/>
        <Main/>
        <Footer/>

    </div>
</template>

<script>
    import TopBar from '@/components/TopBar.vue'
    import Main from '@/components/Main.vue'
    import NewComer from '@/components/NewComer.vue'
    import Footer from '@/components/Footer.vue'

    export default {
        name:'index',
        components:{
            TopBar,
            Main,
            NewComer,
            Footer,
        }
    }
</script>

<style scoped lang="scss">
.index{
    background-color: #f8fafc;
    font-family: 微软雅黑;
}

</style>
