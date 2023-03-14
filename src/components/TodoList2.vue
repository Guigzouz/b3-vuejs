<script>
import TodoItem from './TodoItem.vue';
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
        startEdit(id){
          this.editIndex = id;
        },
        editTask(index){
          this.items[index].label = this.editItemName,
          this.editIndex = -1
        },

        clearAll(){
          this.items = []
        },

        clearDone(){
          if(this.items.done == true){
            this.items = []
          }
        },
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
            <input type="checkbox" id="scales" name="scales" :checked="done">
            <label for="scales">{{item.label}}</label>
            
            <button @click="startEdit(index)" v-if="editIndex !== index">Edit</button>
            <input v-else type="text" v-model="editItemName" />
            <button @click="editTask(index)" v-if="editIndex == index">Save</button>

          </li>
        </ul>
        <button @click="clearAll()">Clear All</button>
        <button @click="clearDone()">Clear Done</button>

      </div>
    
    
    </template>