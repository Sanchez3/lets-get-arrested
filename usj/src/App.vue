<template>
    <div id="app">
        <HelloWorld msg="Universal Studios Japan" />
        <div class="alerts-wrapper">
            <Alerts v-bind:question="question" />
        </div>
    </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue'
import Alerts from './components/Alerts.vue'
export default {
    name: 'app',
    data: function() {
        return {
            time0: 0,
            time1: 0,
            question: [
                { q: 'Go To USJ?', a1: 'Yeah!', a2: 'Must do!' },
                { q: '早餐哪吃?', a1: 'LAWSON', a2: '7-Eleven' },
                { q: '咋去?', a1: '地铁', a2: '打的，壕' },
                { q: '到达USJ，买个票', a1: 'Express快速票', a2: '仅门票' },
                { q: '', a1: 'Express快速票', a2: '仅门票' },


            ]
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
        HelloWorld,
        Alerts

    }
}
</script>
<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #000000;
    margin-top: 60px;
}

.alerts-wrapper {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.6);
}
</style>