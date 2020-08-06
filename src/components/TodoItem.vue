<template>
  <div>
    <ul>
      <li class="todo-item">
        <input class="checkbox" type="checkbox" @click="markComplete" />
        <span v-bind:class="{ 'is-complete': todo.completed }">{{
          todo.title
        }}</span>
        <button @click="$emit('del-todo', todo.id)">Delete</button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
};
</script>

<style scoped>
ul {
  list-style: none;
}
.checkbox {
  margin-right: 0.3rem;
}
.is-complete {
  text-decoration: line-through;
}
</style>
