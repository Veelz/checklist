<template>
  <form>
    <div class="row-2">
        <input id="new-todo" v-model="newTodo" placeholder="What's need to be done?">
        <button class="button" type="button" @click="createNewTodo">Add</button>
    </div>
  </form>
</template>

<script>
export default {
    emits: ['newTodoCreated'],
    data() {
        return {
            newTodo: ''
        }
    },
    methods: {
        createNewTodo() {
            if (!this.newTodo) return;
            this.$emit("newTodoCreated", this.newTodo); 
            this.newTodo = '';
        }
    }
}
</script>

<style>

</style>