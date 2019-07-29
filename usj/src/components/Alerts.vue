<template>
    <div class="alerts">
        <div class="alerts-content">{{question[0].q}}</div>
        <div class="action1" @click.self="doAction1" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover">{{question[0].a1}}</div>
        <div class="action2" @click.self="doAction2" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover">{{question[0].a2}}</div>
    </div>
</template>
<script>
export default {
    name: 'Alerts',
    props: {
        question: Array
    },
    methods: {
        doAction1: function() {

        },
        doAction2: function() {

        },
        doHover: function(event) {
            event.target.classList.add('hover')
        },
        disHover: function(event) {
            event.target.classList.remove('hover')
        }
    }

}
</script>
<style scoped>
.alerts {
    position: absolute;
    width: 270px;
    height: 140px;
    background-color: rgba(248, 248, 248, 0.82);
    border-radius: 14px;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    margin: auto;
    overflow: hidden;
}

.alerts-content {
    margin-top: 20px;
    margin-left: 16px;
    margin-right: 16px;
    font-size: 17px;
    font-weight: bold;
}

.action1 {
    padding-top: 13px;
    font-size: 17px;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 134.75px;
    height: 44px;
    border-top: 0.5px solid #000;
    border-right: 0.25px solid #000;
    color: #007AFF;
    user-select: none;
}

.hover {
    background-color: rgba(234, 234, 234, 0.82);
}

.action2 {
    padding-top: 13px;
    font-size: 17px;
    position: absolute;
    bottom: 0;
    right: 0;
    width: 134.75px;
    height: 44px;
    border-top: 0.5px solid #000;
    border-left: 0.25px solid #000;
    color: #007AFF;
    user-select: none;
}
</style>