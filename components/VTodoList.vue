<template>
  <section class="todoList">
    <ul class="todoList__container">
      <li v-for="(todo, i) in todos" :key="i" class="todoList__item">
        <input type="checkbox" :checked="todo.isDone">
        <input type="text" :value="todo.title" class="todoList__input">
        <button class="todoList__button">編集</button>
        <button class="todoList__button">削除</button>
      </li>
    </ul>
  </section>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend ({
  props: {
    'todos': Array
  }
})
</script>

<style lang="scss" scoped>
.todoList {
  
  &__item {
    list-style: none;
  }

  &__input {
    text-align: center;
    border: solid 1px #000;
  }

  &__button {
    border: solid 1px #000;
  }
}
</style>
