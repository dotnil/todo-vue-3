<template>
  <li class="todo-list__item">
    <span
      class="todo-list__item-name"
      :class="{ 'todo-list__item-name_completed': todo.done }"
      @click="toggleTask"
      >{{ todo.name }}</span
    >
    <a class="todo-list__delete" href="#" @click="deleteTask">×</a>
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
.todo-list__item-name {
  cursor: pointer;
}
.todo-list__item-name_completed {
  text-decoration: line-through;
}
.todo-list__delete {
  font-size: 130%;
  text-decoration: none;
  color: #2c3e50;
  margin-left: 10px;
}
.todo-list__delete:hover {
  color: #9e0020;
}
</style>
