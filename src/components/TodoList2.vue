<script>
import TodoItem from './TodoItem.vue';
export default {
    data() {
        return {
            items: [
                {label : 'foo', done: false, id: 1}
            ],
            newItemName: ""
        }
    },

    methods: {
        addTask(){
            this.items.push({
                label: this.newItemName,
            });
        }
    },

    components: {
        TodoItem
    }
}


</script>

<template>


    <div id="app">
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


        <ul>
          <li style="display: flex; justify-content: space-between;" v-for="(item, index) in items" :key="index">
            <TodoItem   
                :label="item.label"
                :done="item.done"
                :id="item.id">>
            </TodoItem>
          </li>
        </ul>
      </div>
    
    
    </template>