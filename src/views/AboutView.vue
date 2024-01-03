<script setup lang="ts">
import TodoPage from '@/components/TodoPage.vue';

</script>
<template>
  <div class="about">
    <TodoPage/>
  </div>
</template>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
