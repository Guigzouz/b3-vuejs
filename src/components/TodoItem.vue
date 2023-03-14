<script setup>
defineProps({
    done: Boolean,
    label: String,
    id: String,
})
</script>

<template>
    <input type="checkbox" id="scales" name="scales" :checked="done">
    <label for="scales">{{label}}</label>
    <button @click="startEdit(index)" v-if="editIndex == index">Edit</button>
    <button @click="startEdit(index)" v-if="editIndex !== index">Save</button>

</template>