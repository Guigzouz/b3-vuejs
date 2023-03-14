<script setup>

</script>

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
          <button type="submit">clear</button>
        </form>
</template>