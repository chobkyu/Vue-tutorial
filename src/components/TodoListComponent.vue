<script setup lang="ts">
import type { todo } from './TodoPage.vue';


const props = defineProps({
    todolist : Array<todo>
})
</script>

<template>
    <ul>
        <li v-for="todo in todolist" :key="todo.id">
            <input type="checkbox" v-model="todo.done"/>
            <span :class="{done: todo.done}">{{ todo.text }}</span>
        </li>
    </ul>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>