<template>
    <div>
        <div class="mickey" :key="index"
             v-for="(item, index) in list"
             @click="onItemClick(index, item)">
            {{item.name}}
        </div>
    </div>
</template>

<script>
    export default {
        name: "TodoList",
        props: {
            list: {
                type: Array,
                required: true,
            },
        },
        methods: {
            onItemClick: function (index, item) {
                this.$emit('onItemClick',index, item);
            }
        }
    }
</script>

<style scoped>
    .mickey {
        cursor: pointer;
    }
</style>
