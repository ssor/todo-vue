<template>
  <input type="text" class="input" :value="value" v-on="listeners" />
</template>

<script>
export default {
  name: "input-text",
  props: {
    value: {
      type: String,
      default: ""
    }
  },
  computed:{
      listeners(){
          return{
              ...this.$listeners,
              input: event=> this.$emit("input", event.target.value)
          }
      }
  }
};
</script>

<style scoped>
.input {
  width: 90%;
  padding: 8px 10px;
  border: 1px solid rgba(10, 10, 10, 1);
}
</style>

