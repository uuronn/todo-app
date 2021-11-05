<template>
  <main class="container">
    <h1>ToDoList</h1>
    <VTodoInput/>
    <VTodoList/>
  </main>
</template>

<script lang="ts">
import Vue from 'vue';
import VTodoInput from '~/components/VTodoInput.vue';
import VTodoList from '~/components/VTodoList.vue';

export default Vue.extend({
  components: {
    VTodoList,
    VTodoInput,
  }
});
</script>

<style lang="scss" scoped>
.container {
  width: 100%;
  height: 100vh;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}
</style>
