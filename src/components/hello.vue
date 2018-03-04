<template>
<div class="wrap">
    <ul>
        <li class="item" v-for="item in text">
            <div class="start">{{item.id}}</div>
            <div class="center">
                <p v-for="(item,index ) in num" @click="chooseOrder($event)">
                    {{item.id}}
                    <input type="checkbox" name="" v-model="val" :value="index">
                </p>
            </div>
            <div class="end">
                <p v-for="(item,index ) in type" @click="selectStyle ($event)" :class="{index}">
                    {{item.id}}
                    <input type="radio" name="" :value="index">
                </p>
            </div>
        </li>
    </ul>
    <!-- <span>{{val}}</span> -->
</div>
</template>
<script>
import Vue from 'vue'
export default {
    data() {
        return {
            val: [],
            active: false,
            text: [{
                    id: '万位'
                },
                {
                    id: '千位'
                },
                {
                    id: '百位'
                },
                {
                    id: '十位'
                },
                {
                    id: '个位'
                }
            ],
            num: [{
                    id: 0,
                    isActive: true
                },
                {
                    id: 1,
                    isActive: false
                },
                {
                    id: 2,
                    isActive: false
                },
                {
                    id: 3,
                    isActive: false
                },
                {
                    id: 4,
                    isActive: false
                },
                {
                    id: 5,
                    isActive: false
                },
                {
                    id: 6,
                    isActive: false
                },
                {
                    id: 7,
                    isActive: false
                },
                {
                    id: 8,
                    isActive: false
                },
                {
                    id: 9,
                    isActive: false
                },

            ],
            type: [{
                    id: '全'
                },
                {
                    id: '大'
                },
                {
                    id: '小'
                },
                {
                    id: '单'
                },
                {
                    id: '双'
                },
                {
                    id: '清'
                },
            ]
        }

    },
    methods: {
        chooseOrder(e) {
            if (e.target.className.indexOf("active") == -1) {
                e.target.className = "active"; //切换按钮样式
            } else {
                e.target.className = ""; //切换按钮样式
            }
        },
        selectStyle(e) {
            if (e.target.className.indexOf("active") == -1) {
                e.target.className = "active"; //切换按钮样式
                console.log(e);
                // var el = e.target.parentNode;
                console.log(e.target.parentNode.childNodes);
                // e.target.parentNode.childNodes.className = "";
            } else {
                e.target.className = ""; //切换按钮样式
            }
        }
    },
    components: {

    }
}
</script>
<style scoped>
.wrap {
    width: 820px;
    height: 270px;
    background: #ffffff;
}

.wrap .item {
    height: 40px;
    margin-bottom: 12px;
}



.wrap .item p.active {
    transition: all 0.4s;
    background: #ea8541;
    color: #fff;
}


.wrap .item p:hover {
    /* transition: all 0.4s;
    background: #ea8541;
    color: #fff; */
    cursor: pointer;
}

.wrap .item div {
    float: left;
}

.wrap .item .start {
    width: 45px;
    height: 40px;
    line-height: 40px;
    text-align: center;
    color: #c77b61;
}

.wrap .item .center {
    width: 454px;
    height: 40px;
    display: -webkit-box;
    -webkit-box-pack: justify;
    -webkit-box-align: center;
}

.wrap .item .center p {
    width: 39px;
    height: 39px;
    line-height: 40px;
    border-radius: 50%;
    font-weight: 700;
    border: 1px solid #d9d9d9;
    text-align: center;
}

.wrap .item .end {
    width: 273px;
    height: 40px;
    padding-left: 48px;
    display: -webkit-box;
    -webkit-box-pack: justify;
    -webkit-box-align: center;
}

.wrap .item .end p {
    width: 32px;
    height: 32px;
    line-height: 32px;
    border-radius: 6px;
    border: 1px solid #d9d9d9;
    text-align: center;
}

.wrap .item .center p input,
.wrap .item .end p input {
    display: none;
    /* opacity: 0; */
}
</style>
