<template>
  <li class="todo-item">
    <span
      class="todo-item__name"
      :class="{ 'todo-item__name_completed': todo.done }"
      @click="toggleTask"
      >{{ todo.name }}</span
    >
    <a class="todo-item__delete" href="#" @click="deleteTask">×</a>
  </li>
</template>

<script>
export default {
  props: {
    index: {
      type: Number,
      default: 0
    },
    todo: {
      type: Object,
      default: () => {}
    }
  },
  methods: {
    deleteTask() {
      this.$emit("deleteTask", this.index)
    },
    toggleTask() {
      this.$emit("toggleTask", this.index)
    }
  }
}
</script>

<style>
.todo-item__name {
  cursor: pointer;
}
.todo-item__name_completed {
  text-decoration: line-through;
}
.todo-item__delete {
  font-size: 130%;
  text-decoration: none;
  color: #2c3e50;
  margin-left: 10px;
}
.todo-item__delete:hover {
  color: #9e0020;
}
</style>
