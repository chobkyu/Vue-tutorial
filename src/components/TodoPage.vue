<script setup lang="ts">
import { ref } from 'vue';
import MyCompoenent from './MyComponent.vue'
import TodoListComponent from './TodoListComponent.vue';

let id = 0;

const newTodo = ref('');
const todos = ref([
    { id: id++, text: 'HTML 배우기' },
    { id: id++, text: 'JavaScript 배우기' },
    { id: id++, text: 'Vue 배우기' }
]);


</script>

<template>
    <MyCompoenent>
        <template #name>조병규</template>
        <template #intro>의 할일이다 임마</template>
    </MyCompoenent>

    <!-- <InputComponent>
    
    </InputComponent>-->

    <TodoListComponent :todolist="todos"/>
    
</template>