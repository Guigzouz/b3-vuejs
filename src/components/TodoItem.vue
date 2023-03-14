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
    <button type="submit">Edit</button>
</template>