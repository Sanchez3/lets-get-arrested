<template>
    <div id="app">
        <HelloWorld msg="Universal Studios Japan" />
        <div class="alerts-wrapper">
            <Alerts v-bind:question="flow" />
        </div>
        <footer><a href="https://movie.douban.com/review/9856170/">流程参考黑镜</a></footer>
    </div>
</template>
<script>
import HelloWorld from './components/HelloWorld.vue'
import Alerts from './components/Alerts.vue'
export default {
    name: 'app',
    data: function() {
        return {
            flow: {
                nodeDataArray: [
                    { key: '0', text: `起床⏰ `, a1: '再睡会儿💤', a2: '立刻马上😑' },
                    { key: '1', text: '早餐哪里吃?', a1: '7-Eleven💚', a2: 'FamilyMart💚💙', a3: 'LAWSON💙' },
                    { key: '2', text: '如何去USJ', a1: '地铁 🚅', a2: '打的 🚕' },
                    { key: '3', text: '到达USJ门口', a1: '冲啊💃 ', a2: '瞻仰🕺' },
                    { key: '4', text: '🚫🍱🥤食べ物や飲み物はありますか？', a1: 'NoNoNo', a2: '？？？' },
                    { key: '5', text: '私自携带盒饭饮料，被工作人员发现END', a1: '🙇🏻', a2: '🙇🏻‍♀️' },
                    { key: '6', text: '凭票入门', a1: '开始我的表演🆒', a2: '' },
                    { key: '7', text: '买Express票吗？', a1: '👌🏻需要吗？', a2: '✋🏻我不需要' },
                    { key: '8', text: 'APP「排队攻略」查看排队时间，>1h', a1: '一定要🎫', a2: '认怂' },
                    { key: '9', text: '「Universal Express」🎫 ', a1: '通行券 4', a2: '通行券 7' },
                    { key: '10', text: '你是穷吧', a1: '我爱排队', a2: '是的🤲🏻' },
                    { key: '11', text: '前面有卖爆米花的🍿', a1: 'GO', a2: '走' },
                    { key: '12', text: '极其NB爆米花桶', a1: 'EVA哥斯拉爆米花桶🦖', a2: 'EVA初号机爆米花桶🤖' },
                    { key: '13', text: '每日限定，售罄', a1: '心态爆炸💥', a2: '哎，好吧' },
                    { key: '14', text: '买买买', a1: '「EVA初号机爆米花桶」💟', a2: '普通爆米花' },
                    { key: '15', text: '真香🤯', a1: '爆米花香', a2: '爆米花桶香' },
                    { key: '16', text: 'WOCA，路人有限定款爆米花桶', a1: '极其嫉妒🤬', a2: '自我安慰🙄' },
                    { key: '17', text: 'USJ体验心态崩溃END', a1: '🌶', a2: '🐔' },
                    { key: '18', text: '随身携带，疯狂把玩桶', a1: '盘之🤪', a2: '' },
                    { key: '19', text: '同伴共享🍿，其乐融融', a1: '👯‍♂️👯‍♀️👯‍♂️', a2: '' },
                    { key: '20', text: '共商下一个目的地', a1: '「环球奇境」', a2: '「哈利波特魔法世界」' },
                    { key: '21', text: '卡哇伊!', a1: '低幼😒', a2: '可爱🤤' },
                    { key: '22', text: '体验下', a1: '我还小👶', a2: '我长大了👨‍🦳' },
                    { key: '23', text: '有一丶丶可爱，羞耻心爆满', a1: '羞于启齿🤫', a2: '' },
                    { key: '24', text: '离开「环球奇境」', a1: '走🚶‍♂️', a2: '跑🏃‍♂️' },
                    { key: '25', text: 'WOW！「会飞的福特汽车」', a1: '逼真🤩', a2: '' },
                    { key: '26', text: '刚刚开始而已📸', a1: '来拍张', a2: '疯狂拍照' },
                    { key: '27', text: '摆个pose', a1: '标准游客🌝', a2: 'xinyu姿势🕺' },
                    { key: '28', text: '巫师们安居的家园——「活米村」', a1: '光顾下🙌🏼', a2: '' },
                    { key: '29', text: '来杯「黄油啤酒」🍺', a1: '不不不，一看就不行', a2: '干了' },
                    { key: '30', text: '🤷‍♀️丧失重要体验🤷‍♂️', a1: '我喝还不成吗', a2: '再见END' },
                    { key: '31', text: '太多了一家挨着一家', a1: '逛之', a2: '' },
                    { key: '32', text: '那里有「鹰马飞行训练」🦅🐎 ！？', a1: '去海格家讨教', a2: '不了不了' },
                    { key: '33', text: '要不再去体验下「环球奇境」👶', a1: '好', a2: '诶呀去去去' },
                    { key: '34', text: '一本满足，继续逛👉', a1: 'i ku so', a2: `Let's go` },
                    { key: '35', text: '「哈利波特禁忌之旅」Express🏰', a1: '斯该', a2: '超逼真超兴奋' },
                    { key: '36', text: '学生贼多，无快速，需等30min👥👥👥', a1: '有序排队', a2: '不得不排队' },
                    { key: '37', text: '开始飞行，抢个位置', a1: '听从安排', a2: '随机随机🎲', a3: '抢不要怂', a4: '讨好sensai' },
                    { key: '38', text: '秩序井然', a1: '👍', a2: '好人卡一张' },
                    { key: '39', text: `第${Math.floor(Math.random()*7)+1}座位，体验佳`, a1: '🤩', a2: '' },
                    { key: '40', text: '注意素质，老末位置', a1: '🙇‍♀️ 我错了', a2: '🙇‍♂️ 我真错了' },
                    { key: '41', text: '你可真是个机灵鬼，第一是你的了', a1: '阿里嘎多', a2: '阿里嘎多够咋衣麻斯' },
                    { key: '42', text: '私って天才!?', a1: 'はい(Hai)🙆‍♂️', a2: 'いいえ🙅‍♂️' },
                    { key: '43', text: '获得”USJ马猴烧酒“称号🧙‍♀️ 🧙‍♂️', a1: '无敌', a2: '哈哈哈' },
                    { key: '44', text: '需要一个魔杖🦴', a1: '买买买', a2: '不，我需要多个' },
                    { key: '45', text: '下面要干什么呢❓', a1: '饿了', a2: '继续继续', a3: 'one more time' },
                    { key: '46', text: '吃什么呢🥢', a1: '「浮桥快餐店」', a2: '不，不饿' },
                    { key: '47', text: '不还是要💆‍♀️休息休息💆‍♂️吃点东西', a1: '就不吃', a2: '吃，真香' },
                    { key: '48', text: '双倍快乐✌️', a1: '根本不会腻', a2: '' },
                    { key: '49', text: '身子骨撑不住了END💀', a1: '我吃还不成吗', a2: '真香' },
                    { key: '50', text: '有点渴，喝点什么', a1: '「jaws冰沙」🥶', a2: '不，不渴' },
                    { key: '51', text: '这设施也太多了，选择困难症🤔', a1: '继续游戏设施', a2: '商店买买买' },
                    { key: '52', text: '我是', a1: '误入魔法世界的麻瓜✋', a2: '沉迷魔法世界的大法师🤚' },
                    { key: '53', text: 'Continue⏯', a1: '迫不及待', a2: '急不可耐' },
                    { key: '54', text: '游戏派出发', a1: '加快⏩', a2: '不慢▶️' },
                    { key: '55', text: '各式各样，琳琅满目♾', a1: '我就试试，不买', a2: '买呀' },
                    { key: '56', text: '麻瓜也有更多快乐', a1: '😊', a2: '' },
                    { key: '57', text: '帮助麻瓜🔮', a1: '“Mobiliarbus”', a2: '“Tarantollegra”' },
                    { key: '58', text: '为何不玩点更刺激的💥', a1: '是', a2: '这TM还用说' },
                    { key: '59', text: '「侏罗纪公园·乘船游」💦', a1: '不了不了', a2: '走着试试' },
                    { key: '60', text: '同伴赞不绝口，互相吹捧', a1: '准备结账💳', a2: '逃离是非之地' },
                    { key: '61', text: '「飞天翼龙」/「好莱坞美梦乘车游玩」', a1: '前者🐲', a2: '后者🎢' },
                    { key: '62', text: '躲过湿身危险⚠️，去', a1: '「小黄人乐园」', a2: '「纽约」' },
                    { key: '63', text: '机不可失，时不再来‼️', a1: '我买还不成吗', a2: '我剁手了' },
                    { key: '64', text: '体验「冰冻极光乘车游」🚙', a1: '不玩白不玩', a2: '白玩谁要玩' },
                    { key: '65', text: '「小黄人调皮闹剧世界」🔫', a1: '冰霜攻击', a2: '嗨就完事了🥳' },
                    { key: '66', text: '开船！！！🚤', a1: '有点平淡', a2: '一般一般' },
                    { key: '67', text: '是顺/逆乘车🔄 ', a1: '我都要', a2: '' },
                    { key: '68', text: '小黄人=小小兵✅', a1: '我早就知道', a2: 'so u de su ne' },
                    { key: '69', text: '「蜘蛛侠惊魂历险记」Express🕷🕸', a1: '我也被蜘蛛咬了', a2: '真棒' },
                    { key: '70', text: '最后是激流勇进啊！🌊', a1: 'WOCA！这太刺激了', a2: '我要下船' },
                    { key: '71', text: '「小黄人调皮闹剧乘车游」Express', a1: '好玩啊🌕', a2: '有待改进🌑' },
                    { key: '72', text: 'biubiu 吐丝丝丝', a1: '🧬', a2: '' },
                    { key: '73', text: '或许是全园最佳项目了💯', a1: '是的', a2: '之一' },
                    { key: '74', text: '🆘空中惊魂，设备故障倒挂半空END', a1: '等待救援', a2: '血液集中头皮毛囊里，头发再生挺好' },
                    { key: '75', text: '上上下下，顺顺逆逆END', a1: '吐了🤮', a2: '没得吐🤢' },
                    { key: '76', text: '体验还是不错的END', a1: '🍌🍌🍌🍌🍌🍌🍌', a2: '' },
                    { key: '77', text: '喜获中二病END', a1: '我还有救👩🏻‍🎤', a2: '我没病👨🏻‍🎤' },
                    { key: '78', text: '回味无穷，疯狂安利END🗣', a1: '我还要去', a2: '一定要去' },
                    { key: '79', text: '毫无防备，湿身了END', a1: '雅蠛蝶🧖‍♀️', a2: 'hazukashii🧖‍♂️' },
                    { key: '80', text: '小孩子才做选择，大人我全都要END', a1: '🔺<br/>🔸<br/>🔵', a2: '◾️<br/>🔸<br/>⬜️' },
                    { key: '81', text: '全球No.1游乐设备体验END', a1: 'Get💮', a2: '' },
                    { key: '82', text: '前期透支过多，京都东京游极为节俭', a1: '💸', a2: '' },
                    { key: '83', text: '赚钱啊💵💴💶💷', a1: '我爱加班END', a2: '我爱上班END' },
                ],
                linkDataArray: [
                    { a1: { from: 0, to: 0 }, a2: { from: 0, to: 1 } },
                    { a1: { from: 1, to: 2 }, a2: { from: 1, to: 2 }, a3: { from: 1, to: 3 } },
                    { a1: { from: 2, to: 3 }, a2: { from: 2, to: 3 } },
                    { a1: { from: 3, to: 4 }, a2: { from: 3, to: 4 } },
                    { a1: { from: 4, to: 5 }, a2: { from: 4, to: 6 } },
                    { a1: { from: 5, to: 100 }, a2: { from: 5, to: 100 } },
                    { a1: { from: 6, to: 7 }, a2: { from: 6, to: 7 } },
                    { a1: { from: 7, to: 8 }, a2: { from: 7, to: 10 } },
                    { a1: { from: 8, to: 9 }, a2: { from: 8, to: 9 } },
                    { a1: { from: 9, to: 11 }, a2: { from: 9, to: 11 } },
                    { a1: { from: 10, to: 8 }, a2: { from: 10, to: 11 } },
                    { a1: { from: 11, to: 12 }, a2: { from: 11, to: 12 } },
                    { a1: { from: 12, to: 13 }, a2: { from: 12, to: 19 } },
                    { a1: { from: 13, to: 14 }, a2: { from: 13, to: 14 } },
                    { a1: { from: 14, to: 15 }, a2: { from: 14, to: 19 } },
                    { a1: { from: 15, to: 16 }, a2: { from: 15, to: 16 } },
                    { a1: { from: 16, to: 17 }, a2: { from: 16, to: 18 } },
                    { a1: { from: 17, to: 100 }, a2: { from: 17, to: 100 } },
                    { a1: { from: 18, to: 19 }, a2: { from: 18, to: 19 } },
                    { a1: { from: 19, to: 20 }, a2: { from: 19, to: 20 } },
                    { a1: { from: 20, to: 21 }, a2: { from: 20, to: 25 } },
                    { a1: { from: 21, to: 22 }, a2: { from: 21, to: 22 } },
                    { a1: { from: 22, to: 23 }, a2: { from: 22, to: 24 } },
                    { a1: { from: 23, to: 21 }, a2: { from: 23, to: 21 } },
                    { a1: { from: 24, to: 28 }, a2: { from: 24, to: 28 } },
                    { a1: { from: 25, to: 26 }, a2: { from: 25, to: 26 } },
                    { a1: { from: 26, to: 27 }, a2: { from: 26, to: 27 } },
                    { a1: { from: 27, to: 28 }, a2: { from: 27, to: 28 } },
                    { a1: { from: 28, to: 29 }, a2: { from: 28, to: 29 } },
                    { a1: { from: 29, to: 30 }, a2: { from: 29, to: 31 } },
                    { a1: { from: 30, to: 29 }, a2: { from: 30, to: 100 } },
                    { a1: { from: 31, to: 32 }, a2: { from: 31, to: 32 } },
                    { a1: { from: 32, to: 36 }, a2: { from: 32, to: 33 } },
                    { a1: { from: 33, to: 34 }, a2: { from: 33, to: 34 } },
                    { a1: { from: 34, to: 35 }, a2: { from: 34, to: 35 } },
                    { a1: { from: 35, to: 44 }, a2: { from: 35, to: 44 } },
                    { a1: { from: 36, to: 37 }, a2: { from: 36, to: 37 } },
                    { a1: { from: 37, to: 38 }, a2: { from: 37, to: 39 }, a3: { from: 37, to: 40 }, a4: { from: 37, to: 41 } },
                    { a1: { from: 38, to: 34 }, a2: { from: 38, to: 34 } },
                    { a1: { from: 39, to: 34 }, a2: { from: 39, to: 34 } },
                    { a1: { from: 40, to: 34 }, a2: { from: 40, to: 34 } },
                    { a1: { from: 41, to: 42 }, a2: { from: 41, to: 42 } },
                    { a1: { from: 42, to: 43 }, a2: { from: 42, to: 34 } },
                    { a1: { from: 43, to: 100 }, a2: { from: 43, to: 100 } },
                    { a1: { from: 44, to: 45 }, a2: { from: 44, to: 45 } },
                    { a1: { from: 45, to: 46 }, a2: { from: 45, to: 47 }, a3: { from: 45, to: 48 } },
                    { a1: { from: 46, to: 50 }, a2: { from: 46, to: 50 } },
                    { a1: { from: 47, to: 49 }, a2: { from: 47, to: 51 } },
                    { a1: { from: 48, to: 52 }, a2: { from: 46, to: 52 } },
                    { a1: { from: 49, to: 100 }, a2: { from: 49, to: 100 } },
                    { a1: { from: 50, to: 53 }, a2: { from: 50, to: 53 } },
                    { a1: { from: 51, to: 54 }, a2: { from: 51, to: 55 } },
                    { a1: { from: 52, to: 56 }, a2: { from: 52, to: 57 } },
                    { a1: { from: 53, to: 58 }, a2: { from: 53, to: 58 } },
                    { a1: { from: 54, to: 59 }, a2: { from: 54, to: 59 } },
                    { a1: { from: 55, to: 60 }, a2: { from: 55, to: 60 } },
                    { a1: { from: 56, to: 81 }, a2: { from: 56, to: 81 } },
                    { a1: { from: 57, to: 81 }, a2: { from: 57, to: 81 } },
                    { a1: { from: 58, to: 61 }, a2: { from: 58, to: 61 } },
                    { a1: { from: 59, to: 62 }, a2: { from: 59, to: 66 } },
                    { a1: { from: 60, to: 63 }, a2: { from: 60, to: 63 } },
                    { a1: { from: 61, to: 74 }, a2: { from: 61, to: 67 } },
                    { a1: { from: 62, to: 64 }, a2: { from: 62, to: 65 } },
                    { a1: { from: 63, to: 80 }, a2: { from: 63, to: 80 } },
                    { a1: { from: 64, to: 68 }, a2: { from: 64, to: 68 } },
                    { a1: { from: 65, to: 69 }, a2: { from: 65, to: 69 } },
                    { a1: { from: 66, to: 70 }, a2: { from: 66, to: 70 } },
                    { a1: { from: 67, to: 75 }, a2: { from: 67, to: 75 } },
                    { a1: { from: 68, to: 71 }, a2: { from: 68, to: 71 } },
                    { a1: { from: 69, to: 72 }, a2: { from: 69, to: 73 } },
                    { a1: { from: 70, to: 79 }, a2: { from: 70, to: 79 } },
                    { a1: { from: 71, to: 76 }, a2: { from: 71, to: 76 } },
                    { a1: { from: 72, to: 77 }, a2: { from: 72, to: 77 } },
                    { a1: { from: 73, to: 78 }, a2: { from: 73, to: 78 } },
                    { a1: { from: 74, to: 100 }, a2: { from: 74, to: 100 } },
                    { a1: { from: 75, to: 100 }, a2: { from: 75, to: 100 } },
                    { a1: { from: 76, to: 100 }, a2: { from: 76, to: 100 } },
                    { a1: { from: 77, to: 100 }, a2: { from: 77, to: 100 } },
                    { a1: { from: 78, to: 100 }, a2: { from: 78, to: 100 } },
                    { a1: { from: 79, to: 100 }, a2: { from: 79, to: 100 } },
                    { a1: { from: 80, to: 82 }, a2: { from: 80, to: 82 } },
                    { a1: { from: 81, to: 100 }, a2: { from: 81, to: 100 } },
                    { a1: { from: 82, to: 83 }, a2: { from: 82, to: 83 } },
                    { a1: { from: 83, to: 100 }, a2: { from: 83, to: 100 } }
                ]
            }
        }
    },
    created: function() {

        // console.log(this.time0)
    },
    mounted: function() {
        this.$nextTick(function() {
            // Code that will run only after the
            // entire view has been rendered
        })
    },
    components: {
        HelloWorld,
        Alerts

    }
}
</script>
<style>
* {
    margin: 0;
    padding: 0;
}

#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #000000;
}

.alerts-wrapper {
    position: absolute;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    /*background-color: rgba(0, 0, 0, 0.6);*/
}

footer {
    position: absolute;
    bottom: 0;
    font-size: 0.5px;
    left: 0;
    right: 0;
    margin: auto;
}
</style>