<template>
  <section>
    <h1>Checklist</h1>
    <hr>
    <div>
        <todo-item @newTodoCreated="addNewTodo"></todo-item>
    </div>
    <div>
        <todo-list :todoItems="todoItems"></todo-list>
    </div>
  </section>
</template>

<script>
import TodoList from './TodoList.vue'
import TodoItem from './TodoItem.vue'

export default {
    name: '',
    data() {
        return {
            todoItems: [{
                text: 'Sample',
                isDone: false,
                isInEditMode: false
            },
            {
                text: 'Sample 2',
                isDone: true,
                isInEditMode: false
            }]
        }
    },
    methods: {
        addNewTodo(todoItemText) {
            const newItem = {
                text: todoItemText, 
                isDone: false, 
                isInEditMode: false
            };
            this.todoItems.push(newItem);
        }
    },
    components: {
        TodoList,
        TodoItem
    }
}
</script>

<style>
.row-2 {
    display: grid;
    grid-template-columns: 1fr 1fr;
    vertical-align: middle;
    margin: 2em;
}

.row-3 {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    vertical-align: middle;
    margin: 2em;
}

.button {
    background-color: #39495c;
    border-radius: 5px;
    color: white;
    text-align: center;
}
</style>