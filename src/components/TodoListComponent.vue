<script setup lang="ts">
import { ref } from 'vue';
import type { todo } from './TodoPage.vue';

const props = defineProps({
    todolist : Array<todo>
});

const hideCompleted = ref(false)

</script>

<template>
    <ul>
        <li v-for="todo in todolist" :key="todo.id">
            <input type="checkbox" v-model="todo.done"/>
            <span :class="{done: todo.done}">{{ todo.text }}</span>
        </li>
    </ul>

    <button @click="hideCompleted = !hideCompleted">
    {{ hideCompleted ? 'Show all' : 'Hide completed' }}
  </button>
</template>

<style>
.done {
  text-decoration: line-through;
}
</style>