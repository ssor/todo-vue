<template>
  <li>{{ todo.text }}</li>
</template>
<script>
export default {
  name: "todo-list-item",
  props: {
    todo: {
      type: Object,
      required: true
    }
  }
};
</script>

<style scoped>
li {
  color: brown;
}
</style>

