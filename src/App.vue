<template>
    <div>
        <div>
            <test msg="Welcome to Your Vue.js App"/>
        </div>
    </div>
</template>

<script>
    //import HelloWorld from './components/HelloWorld.vue'
    //import runningcat from './components/runningcat.vue'
    import test from './components/test.vue'

    export default {
        name: 'App',
        components: {
            test
        }
    }
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
