<template>
<div class="wrap">
    <ul>
        <li class="item" v-for="item in text">
            <div class="start">{{item.id}}</div>
            <div class="center">
                <p v-for="(item,index ) in num" @click="toggle(item)">
                    {{item.id}}
                    <input type="checkbox" name="" v-model="val" :value="index">
                </p>
            </div>
            <div class="end">
                <p v-for="(item,index ) in type">{{item.id}}
                    <input type="radio" name="" :value="index">
                </p>
            </div>
        </li>
    </ul>
</div>
</template>
<script>
export default {
    data() {
        return {
            val: [],
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
                    isActive: false
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
        toggle: function(item) {
            item.isActive = !item.isActive;
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

.wrap .item p:hover {
    transition: all 0.4s;
    background: #ea8541;
    color: #fff;
    cursor: pointer;
}

.wrap .item p span {
    display: block;
    width: 100%;
    height: 100%;
    transition: all 0.4s;
    background: #ea8541;
    color: #fff;
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
}
</style>
