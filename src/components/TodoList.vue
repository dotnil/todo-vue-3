<template>
  <div class="todo-list">
    <div class="todo-list__wrapper">
      <h1 class="todo-list__header">Todo List</h1>

      <ul class="todo-list__container">
        <TodoItem
          v-for="(todo, index) in todos"
          :key="index"
          :todo="todo"
          :index="index"
          @deleteTask="deleteTask"
          @toggleTask="toggleTask"
        />
      </ul>
      <input v-model="newTask" class="todo-list__new" />
      <div><a href="#" class="todo-list__save-new" @click="saveTask">Save</a></div>
    </div>
  </div>
</template>

<script>
import TodoItem from "@/components/TodoItem.vue"
export default {
  components: {
    TodoItem
  },
  data() {
    return {
      todos: [
        { name: "function", done: false },
        { name: "take a rest", done: false }
      ],
      newTask: ""
    }
  },
  methods: {
    saveTask() {
      this.todos.push({ name: this.newTask })
      this.newTask = ""
    },
    deleteTask(indexForDeletion) {
      this.todos = this.todos.filter((_todo, index) => index !== indexForDeletion)
    },
    toggleTask(indexForToggle) {
      this.todos = this.todos.map((todo, index) => {
        if (index !== indexForToggle) {
          return todo
        }

        return { name: todo.name, done: !todo.done }
      })
    }
  }
}
</script>

<style>
.todo-list {
  font-family: ‘Courier New’, Courier, monospace;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}
.todo-list__wrapper {
  color: #2c3e50;
  background-color: rgba(255, 255, 255, 0.4);
  padding: 20px;
  max-width: 50ch;
}
.todo-list__header {
  font-weight: normal;
  margin-top: 0px;
}
.todo-list__container {
  margin: 0;
  padding: 0;
  list-style-position: inside;
}
.todo-list__new {
  margin: 20px 0px 20px 0px;
  width: 100%;
  box-sizing: border-box;
}

.todo-list__save-new {
  text-decoration: none;
  display: inline-block;
  padding: 10px 15px;
  position: relative;
  color: #2c3e50;
  border: 1px solid #2c3e50;
  background: none;
  font-weight: 300;
  text-transform: uppercase;
  letter-spacing: 2px;
}
.todo-list__save-new:hover {
  background: rgba(255, 255, 255, 0.6);
}
</style>
