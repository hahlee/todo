<template>
  <div class="about">
    <Header />
    <h1>About</h1>
    <p>This is my Todo List app v1.0.0. It uses <a href="https://jsonplaceholder.typicode.com/" target="_blank">JSON Placeholder</a> as the API</p>
  </div>
</template>

<script>
import Header from "@/components/layout/Header";
export default {
  name: "About",
  components: {
    Header
  }
}
</script>


<style lang="sass" scoped>
  @import '@/styles/global.sass'
</style>
