<template>
  <li>
    {{ todo.text }}
    <button @click="removeItem( todo.id )">X</button>
  </li>
</template>
<script>
export default {
  name: "todo-list-item",
  props: {
    todo: {
      type: Object,
      required: true
    }
  },
  methods: {
    removeItem(id) {
      this.$emit("remove", id);
      window.console.log("item trigger remove id ", id);
    }
  }
};
</script>

<style scoped>
li {
  color: brown;
}
</style>

