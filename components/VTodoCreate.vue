<template>
  <section class="todoCreate">
    <div class="todoCreate__container">
      <input class="todoCreate__input" v-model="todoTitle" type="text">
      <button class="todoCreate__button" @click="addTodo">追加</button>
    </div>
  </section>
</template>

<script>
export default ({
  data() {
    return {
      todoTitle: ""
    }
  },
  methods: {
    addTodo() {
      if(this.todoTitle) {
        console.log(this.todoTitle);
      }
        this.todoTitle = "";
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
