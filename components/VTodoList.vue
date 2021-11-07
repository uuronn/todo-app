<template>
  <section class="todoList">
    <ul class="todoList__container">
      <li v-for="(todo, i) in todos" :key="i" class="todoList__item">
        <input type="checkbox" :checked="todo.isDone" @change="changeDone(i)">
        <input type="text" v-model="todo.title" class="todoList__input">
        <button class="todoList__button" @click="updateTitle(i)">更新</button>
        <button class="todoList__button">削除</button>
      </li>
    </ul>
  </section>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue';

interface Todo {
  id: number;
  title: string;
  isDone: boolean;
}

export default Vue.extend({
  props: {
    todos: {
      type: Array as PropType<Todo[]>
    }
  },
  methods: {
    // 更新
    async updateTitle(i: number) {
      const response = await this.$axios.$patch(`https://yukinissie.dev/api/todos/${this.todos[i].id}`,{title: this.todos[i].title, isDone: this.todos[i].isDone});
      console.log(response);
      console.log(i)
    },
    // チェックボックス
    async changeDone(i: number) {
      const response = await this.$axios.$patch(`https://yukinissie.dev/api/todos/${this.todos[i].id}`,{title: this.todos[i].title, isDone: !this.todos[i].isDone});
      console.log(response)
      console.log(i)
    }
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
