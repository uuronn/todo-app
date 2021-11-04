<template>
  <main class="container">
    <h1>Hello, Nuxt template!!!</h1>
    <p>by {{ companyName }}</p>
  </main>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  data() {
    return {
      companyName: "Hack'z Inc.",
    };
  },
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
