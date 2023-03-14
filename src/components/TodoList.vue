<script setup>
import TodoForm from './TodoForm.vue';
import TodoItem from './TodoItem.vue';
import { ref } from 'vue';


const items = ref([
    {label : 'foo', done: false, id: 1}
]);
const newItemName = ref('');

const addTask = () => {
  items.value.push({
    label: newItemName,
  });
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
        autocomplete="off" />
      <button type="submit">Add</button>
    </form>
    <ul>
      <li v-for="(item, index) in items" :key="index">
        <TodoItem   
            :label="item.label"
            :done="item.done"
            :id="item.id">>
        </TodoItem>
      </li>
    </ul>
  </div>


</template>