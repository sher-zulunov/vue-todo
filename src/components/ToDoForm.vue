<template>
  <form @submit.prevent="onSubmit">
    <h2 class="label-wrapper"></h2>
    <label for="new-todo-input" class="label__lg">What need to be done?</label>
    <input
      type="text"
      name="new-todo"
      id="new-todo-input"
      autocomplete="off"
      v-model.lazy.trim="label"
      class="input__lg"
    />
    <button type="submit" class="btn btn__primary btn__lg">Add</button>
  </form>
</template>
<script>
export default {
  name: "ToDoForm",
  methods: {
    onSubmit() {
      if (this.label === "") {
        return;
      }
      this.$emit("todo-added", this.label);
      this.label = "";
    },
  },
  data() {
    return {
      label: "",
    };
  },
};
</script>