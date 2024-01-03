<script setup lang="ts">
const props = defineProps({
    todolist : Array
})
</script>

<template>
    {{ todolist ||'not prop' }}
</template>