<template>
    <div>
        <div class="row-3" v-for="(item, index) in todoItems" :key="index">
            <input type="checkbox" v-model="item.isDone">
            <div>
                <span :class="{'todo-item-is-done': item.isDone}" v-show="!item.isInEditMode">
                    {{ item.text }}
                </span>
                <input v-show="item.isInEditMode" v-model="item.text">
            </div>
            <button v-show="!item.isInEditMode" class="button" type="button" @click="enterEditMode(index)">Edit</button>
            <button v-show="item.isInEditMode" class="button" type="button" @click="saveEditTodo(index)">Save</button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        todoItems: Array
    },

    methods: {
        enterEditMode(index) {
            this.todoItems[index].isInEditMode = true;
        },

        saveEditTodo(index) {
            this.todoItems[index].isInEditMode = false;
        }
    }
}
</script>

<style>
.todo-item-is-done {
    text-decoration: line-through
}
</style>