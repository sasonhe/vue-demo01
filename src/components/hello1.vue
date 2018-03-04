<template>
<div class="wrap">
    <ul id="app">
        <li v-for='item in items' @click="toggle(item)">
            <span v-if='item.show'>{{item.content}}</span>
        </li>
    </ul>
</div>
</template>
<script>
import Vue from 'vue'
export default {
    data() {
        return {
            items: [{
                    content: '1 item',
                    content: '1 item',
                    show: true
                },
                {
                    content: '2 item',
                    show: true
                },
                {
                    content: '3 item',
                    show: true
                }
            ]
        }

    },
    methods: {
        toggle: function(item) {
            item.show = !item.show;
        }
    },
    components: {

    }
}
</script>
<style scoped>
ul {
    list-style: none;
    padding: 0;
    margin: 0;
}

ul li {
    padding: 10px;
    border-bottom: 1px dashed grey;
}
</style>
