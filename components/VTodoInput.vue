<template>
  <section class="todoInput">
    <div class="todoInput__container">
      <input class="todoInput__input" v-model="inputName" type="text">
      <button class="todoInput__button" @click="addTodo">追加</button>
    </div>
  </section>
</template>

<script>
export default ({
  data() {
    return {
      inputName: ""
    }
  },
  methods: {
    addTodo() {
      if(this.inputName) {
        console.log(this.inputName);
      }
        this.inputName = "";
    }
  }
})
</script>

<style lang="scss" scoped>
.todoInput {

  &__input {
    border: solid 1px #000;
  }

  &__button {
    border: solid 1px #000;
  }
}
</style>
