<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <input type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed">
        {{todo.title}}
        <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
.todo-item {
    text-align: left;
    margin: auto;
    padding: 10px;
    background: #edfff8;
    border: 1px solid #c4dad1;
}

.is-complete {
    text-decoration: line-through;
}

.del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 3px 8px;
    border-radius: 100%;
    cursor: pointer;
    float: right;
}
</style>
