<template>
    <div id="app">

        <HelloWorld/>
    </div>
</template>

<script>
    import HelloWorld from './components/HelloWorld.vue'

    export default {
        name: 'App',
        components: {
            HelloWorld
        },

    }
</script>

<style lang="less">
    html body{
        margin: 0;
        padding: 0;
    }
    #app{
        width: 100%;
        height: 100%;
    }
</style>
