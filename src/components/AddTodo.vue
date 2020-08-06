<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        name="tite"
        v-model="title"
        placeholder="add todo..."
      />
      <input type="submit" value="submit" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: ""
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      if (this.title !== "") {
        let newTodo = {
          title: this.title,
          completed: false
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      }
    }
  }
};
</script>

<style lang="scss" scoped></style>
