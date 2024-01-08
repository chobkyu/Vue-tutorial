<script setup lang="ts">
import { ref, type Ref } from 'vue';
import MyCompoenent from './MyComponent.vue'
import TodoListComponent from './TodoListComponent.vue';
import InputComponent from './InputComponent.vue';

let id = 0;

export interface todo {
    id:number,
    text:string,
    done:boolean
}

const newTodo = ref('');
const todos :Ref<todo[]>= ref([
    { id: id++, text: 'HTML 배우기',done:false },
    { id: id++, text: 'JavaScript 배우기' ,done:false},
    { id: id++, text: 'Vue 배우기' ,done:false}
]);

const addTodo = (msg:any) => {
    let newTodo = msg._rawValue;
    todos.value.push({
        id:id++,
        text:newTodo,
        done:false
    })
}


</script>

<template>
    <MyCompoenent>
        <template #name>조병규</template>
        <template #intro>의 할일이다 임마</template>
    </MyCompoenent>

    <InputComponent @response="(msg) => addTodo(msg)">
    
    </InputComponent>

    <TodoListComponent :todolist="todos"/>
    


</template>