<template>
    <div class="alerts">
        <div class="alerts-content">{{question.nodeDataArray[count].text}}</div>
        <div class="alerts-choices">
            <div v-if="question.nodeDataArray[count].a1&&question.nodeDataArray[count].a1!==''" class="action1" @click.self="doAction1" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover">{{question.nodeDataArray[count].a1}}</div>
            <div v-if="question.nodeDataArray[count].a2&&question.nodeDataArray[count].a2!==''" class="action2" @click.self="doAction2" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover">{{question.nodeDataArray[count].a2}}</div>
            <div v-if="question.nodeDataArray[count].a3&&question.nodeDataArray[count].a3!==''" class="action3" @click.self="doAction2" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover">{{question.nodeDataArray[count].a3}}</div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Alerts',
    data: function() {
        return {
            count: 0
        }
    },
    props: {
        question: Object
    },
    methods: {
        doAction1: function(count) {
            // console.log(this.$props.question.linkDataArray[this.count].a1.to)
            this.count = this.$props.question.linkDataArray[this.count].a1.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
            }

        },
        doAction2: function() {
            // console.log(this.$props.question.linkDataArray[this.count].a2.to)
            this.count = this.$props.question.linkDataArray[this.count].a2.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
            }
        },
        doAction3: function() {
            // console.log(this.$props.question.linkDataArray[this.count].a3.to)
            this.count = this.$props.question.linkDataArray[this.count].a3.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
            }
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
    background-color: rgba(248, 248, 248, 1);
    border-radius: 14px;
    left: 0;
    right: 0;
    /*top: 0;*/
    bottom: 20%;
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

.alerts-choices {
    display: flex;
    flex-direction: row;
    position: absolute;
    height: 44px;
    border-top: 0.5px solid #000;
    bottom: 0;
    width: 100%;
}

.action1 {
    flex-grow: 1;
    padding-top: 13px;
    font-size: 14px;
	height: 100%;
    color: #007AFF;
    user-select: none;
}

.action2 {
    flex-grow: 1;
    padding-top: 13px;
    font-size: 14px;
    height: 100%;
    color: #007AFF;
    user-select: none;
}

.action3 {
    flex-grow: 1;
    padding-top: 13px;
    font-size: 14px;
    color: #007AFF;
    height: 100%;
    user-select: none;
}
.hover {
    background-color: rgba(234, 234, 234, 1);
}
</style>