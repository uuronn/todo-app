<template>
  <main class="container">
    <h1>ToDoList</h1>
    <VTodoCreate/>
    <VTodoList/>
  </main>
</template>

<script lang="ts">
import Vue from 'vue';
import VTodoCreate from '~/components/VTodoCreate.vue';
import VTodoList from '~/components/VTodoList.vue';

export default Vue.extend({
  components: {
    VTodoList,
    VTodoCreate,
  },
  async asyncData({ app }) {
    const response = await app.$axios.$get('https://yukinissie.dev/api/todos');
    console.log(response);
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
