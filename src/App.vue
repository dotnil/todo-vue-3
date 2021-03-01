<template>
  <TodoList />
</template>

<script>
import TodoList from "./components/TodoList.vue"

export default {
  name: "App",
  components: {
    TodoList
  }
}
</script>

<style>
#app {
  color: #2c3e50;
  padding: 30px;
}
body {
  background-image: linear-gradient(35deg, #fdfcfb 0%, #e2d1c3 100%);
}
</style>
