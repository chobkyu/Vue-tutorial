<script setup lang="ts">
    import { ref } from 'vue';

    const emit = defineEmits(['response']);
    let newTodo = ref('');

    const addTodo = () => {
        emit('response',newTodo)
        newTodo.value='';
    }

</script>

<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo">
    <button>Add Todo</button>
  </form>
</template>