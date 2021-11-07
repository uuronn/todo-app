<template>
  <section class="todoList">
    <ul class="todoList__container">
      <li class="todoList__item" v-for="(todo, i) in todos" :key="i">
        <input class="todoList__checkbox" type="checkbox" :checked="todo.isDone" @change="changeDoneStatus(i)">
        <input class="todoList__input" type="text" v-model="todo.title">
        <button class="todoList__button" @click="updateTodoTitle(i)">更新</button>
        <button class="todoList__button" @click="deleteTodo(i)">削除</button>
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
    async updateTodoTitle(i: number) {
      const response = await this.$axios.$patch(`https://yukinissie.dev/api/todos/${this.todos[i].id}`,{title: this.todos[i].title, isDone: this.todos[i].isDone});
      console.log(response);
      console.log(i)
    },
    // チェックボックス
    async changeDoneStatus(i: number) {
      const response = await this.$axios.$patch(`https://yukinissie.dev/api/todos/${this.todos[i].id}`,{title: this.todos[i].title, isDone: !this.todos[i].isDone});
      console.log(response)
      console.log(i)
    },
    // 削除
    async deleteTodo(i: number) {
      const response = await this.$axios.$delete(`https://yukinissie.dev/api/todos/${this.todos[i].id}`);
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
