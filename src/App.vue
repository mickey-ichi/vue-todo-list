<template>
    <div id="app">
        <img alt="Vue logo" src="./assets/logo.png">
        <TodoList v-bind:list="todos" @onItemClick="onTodoClick"/>
    </div>
</template>

<script>
    import TodoList from './components/TodoList.vue'

    export default {
        name: 'app',
        components: {
            TodoList,
        },
        data: function () {
            return {
                todos: [{name: 'mickey'}],
            }
        },
        mounted: function () {
            setTimeout(() => {
                this.todos.push({
                    name: 'mickey',
                })
            }, 2000);
        },
        methods: {
            onTodoClick: function (index, item) {
                this.$set(this.todos, index, {
                    name: `${item.name} hehe`
                });
            }
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
