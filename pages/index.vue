<template>
  <main class="container">
    <h1 class="title">World ToDo</h1>
    <VTodoCreate/>
    <VTodoList :todos="todos"/>
  </main>
</template>

<script lang="ts">
import Vue from 'vue'
import VTodoCreate from '~/components/VTodoCreate.vue'
import VTodoList from '~/components/VTodoList.vue'

export default Vue.extend({
  components: {
    VTodoCreate,
    VTodoList,
  },
  async asyncData({ app }) {
    try {
      const response = await app.$axios.$get('https://yukinissie.dev/api/todos')
      return {todos: response}
    } catch {
      alert("Error by index")
    }
  }
})
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
