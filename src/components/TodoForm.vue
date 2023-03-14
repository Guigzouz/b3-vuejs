<template>

      <h1>My To-Do List</h1>
      <form @submit.prevent="addTask">
        <label for="new-todo-input"> Add Task </label>
        <input
          type="text"
          id="new-todo-input"
          name="new-todo"
          autocomplete="off"
          v-model="newItemName"
          />
        <button type="submit">Add</button>
      </form>
</template>

<script>
export default {
    data() {
        return {  
          items: [],
          newItemName: "",
          editItemName: "",
            editIndex: -1,
            id: 0,
        }
    },
    methods: {
        addTask(){
            this.items.push({
                label: this.newItemName,
                done: false,
                id: this.id++
            });
        },
      },
    }
</script>