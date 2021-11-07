<template>
  <section class="todoCreate">
    <div class="todoCreate__container">
      <input class="todoCreate__input" v-model="todoTitle" type="text">
      <button class="todoCreate__button" @click="addTodo">追加</button>
    </div>
  </section>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return {
      todoTitle: ""
    }
  },
  methods: {
    async addTodo() {
      console.log(this.todoTitle)
      const response = await this.$axios.$post('https://yukinissie.dev/api/todos',{title: this.todoTitle});
      console.log(response)
    }
  }
})
</script>

<style lang="scss" scoped>
.todoCreate {
  &__input {
    border: solid 1px #000;
  }

  &__button {
    border: solid 1px #000;
  }
}
</style>
