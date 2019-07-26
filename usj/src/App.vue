<template>
    <div id="app">
        <HelloWorld msg="Universal Studios Japan" />
    </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
    name: 'app',
    data: function() {
        return {
            time0: 0,
            time1: 0
        }
    },
    created: function() {
        this.time0 = new Date().getSeconds()
        // console.log(this.time0)
    },
    mounted: function() {
        this.$nextTick(function() {
            // Code that will run only after the
            // entire view has been rendered
            this.time1 = new Date().getSeconds()
            // console.log(this.time1)
            // console.log(this.time1 - this.time0)
        })
    },
    components: {
        HelloWorld
    }
}
</script>
<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>