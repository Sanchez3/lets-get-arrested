<template>
    <div class="alerts">
        <div class="alerts-content">
            <span v-if="question.nodeDataArray[count].key==='0'">{{`${time}:00 `+question.nodeDataArray[count].text}}</span>
            <span v-else>{{question.nodeDataArray[count].text}}</span>
        </div>
        <div class="alerts-choices">
            <div v-if="question.nodeDataArray[count].a1&&question.nodeDataArray[count].a1!==''" class="action1" @click.self="doAction1" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover"><span v-html="question.nodeDataArray[count].a1"></span></div>
            <div v-if="question.nodeDataArray[count].a2&&question.nodeDataArray[count].a2!==''" class="dline"></div>
            <div v-if="question.nodeDataArray[count].a2&&question.nodeDataArray[count].a2!==''" class="action2" @click.self="doAction2" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover"><span v-html="question.nodeDataArray[count].a2"></span></div>
            <div v-if="question.nodeDataArray[count].a3&&question.nodeDataArray[count].a3!==''" class="dline"></div>
            <div v-if="question.nodeDataArray[count].a3&&question.nodeDataArray[count].a3!==''" class="action3" @click.self="doAction3" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover"><span v-html="question.nodeDataArray[count].a3"></span></div>
            <div v-if="question.nodeDataArray[count].a4&&question.nodeDataArray[count].a4!==''" class="dline"></div>
            <div v-if="question.nodeDataArray[count].a4&&question.nodeDataArray[count].a4!==''" class="action4" @click.self="doAction4" @touchstart.self="doHover" @touchend.self="disHover" @mouseenter.self="doHover" @mouseleave.self="disHover"><span v-html="question.nodeDataArray[count].a4"></span></div>
        </div>
    </div>
</template>
<script>
export default {
    name: 'Alerts',
    data: function() {
        return {
            count: 0,
            time: 6
        }
    },
    props: {
        question: Object,
    },
    methods: {
        doAction1: function() {
            if (this.count == 0) {
                this.time++;
                if (this.time > 12) {
                    alert('睡吧别起来了')
                    this.count = 0
                    this.time = 6
                }
            }

            this.count = this.$props.question.linkDataArray[this.count].a1.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
                this.time = 6

            }
            event.target.classList.remove('hover')

        },
        doAction2: function() {
            // console.log(this.$props.question.linkDataArray[this.count].a2.to)
            this.count = this.$props.question.linkDataArray[this.count].a2.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
                this.time = 6
            }
            event.target.classList.remove('hover')
        },
        doAction3: function() {
            // console.log(this.$props.question.linkDataArray[this.count].a3.to)
            this.count = this.$props.question.linkDataArray[this.count].a3.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
                this.time = 6
            }
            event.target.classList.remove('hover')
        },
        doAction4: function() {
            // console.log(this.$props.question.linkDataArray[this.count].a3.to)
            this.count = this.$props.question.linkDataArray[this.count].a4.to
            if (this.count == 100) {
                alert('这是谁写的BUG')
                this.count = 0
                this.time = 6
            }
            event.target.classList.remove('hover')
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
    align-items: center;

}

.action1 {
    flex-grow: 1;
    align-self: center;
    line-height: 100%;
    font-size: 14px;
    height: 100%;
    color: #007AFF;
    text-align: center;
}

.alerts-choices span {
    line-height: 300%;
    user-select: none;
    pointer-events: none;

}

.dline {
    position: relative;

    /*position: absolute;*/
    left: 0;
    top: 0;
    width: 0.5px;
    height: 100%;
    border-left: 0.5px solid #000;
}

.action2 {
    flex-grow: 1;
    line-height: 100%;
    font-size: 14px;
    height: 100%;
    color: #007AFF;
    user-select: none;
}

.action3 {
    flex-grow: 1;
    line-height: 100%;
    font-size: 14px;
    color: #007AFF;
    height: 100%;
    user-select: none;
}

.action4 {
    flex-grow: 1;
    line-height: 100%;
    font-size: 14px;
    color: #007AFF;
    height: 100%;
    user-select: none;
}

.hover {
    background-color: rgba(234, 234, 234, 1);
}
</style>