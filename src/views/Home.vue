<template>
<div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h3>自定义组件</h3>
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <h3>数组遍历</h3>
    <ul id="example-1">
        <li v-for="item in items" :key="item.id">
            {{ item.message }}
        </li>
    </ul>
    <h3>自定义组件 - 事件emit</h3>
    <List :todos="todos" test="001" />
    <h3>自定义组件 - model双向绑定</h3>
    <custom-input v-model="inputValue" />{{inputValue}}
    <button v-on:click="clear">clear</button>
    <h3>自定义组件 - Sync双向绑定</h3>
    {{title}}
    <Sync v-bind:title.sync="title" />
     <h3>自定义组件 - Eventbus</h3>
    <ShowMessage />
    <UpdateMessage />
</div>
</template>

<script>
/* eslint-disable */
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import List from '@/components/List.vue'
import CustomInput from '@/components/CustomInput.vue'
import Sync from '@/components/Sync.vue'
import UpdateMessage from '@/components/UpdateMessage.vue'
import ShowMessage from '@/components/ShowMessage.vue'

export default {
    name: 'home',
    components: {
        HelloWorld,
        List,
        CustomInput,
        Sync,
        UpdateMessage,
        ShowMessage
    },
    data() {
        return {
            items: [{
                message: 'foo',
                id: '1'
            }, {
                message: 'bar',
                id: "2"
            }],
            inputValue: '1',
            todos: [{
                    id: 1,
                    title: 'Do the dishes',
                },
                {
                    id: 2,
                    title: 'Take out the trash',
                },
                {
                    id: 3,
                    title: 'Mow the lawn'
                }
            ],
            title: 'first',
        }
    },
    methods: {
        clear: function () {
            this.inputValue = ''
        }
    }
}
</script>
