<template >
  <div>
    <input-text placeholder="Add a Todo" v-model="newTodoText" @keydown.enter="addTodo" />
    <ul v-if="items.length > 0">
      <todo-list-item v-for="item in items" :key="item.id" :todo="item"></todo-list-item>
      <!-- <li v-for="item in items" v-bind:key="item.id">{{ item.text }}</li> -->
    </ul>
  </div>
</template>

<script>
import InputText from "./input_text";
import TodoListItem from "./todo_list_item";

let nextTodoId = 3;

export default {
  name: "todo-list",
  components: {
    InputText,
    TodoListItem
  },
  data() {
    return {
      newTodoText: "",
      items: [
        { id: 0, text: "todo0" },
        { id: 1, text: "todo1" },
        { id: 2, text: "todo2" }
      ]
    };
  },
  methods: {
    addTodo() {
      let trimmedText = this.newTodoText.trim();
      if (trimmedText.length > 0) {
        window.console.log("add new todo: ", trimmedText);
        this.items.push({ id: nextTodoId, text: trimmedText });

        nextTodoId += 1;
        this.newTodoText = "";
      } else {
        window.console.log("no content for todo");
      }
    }
  }
};
</script>
