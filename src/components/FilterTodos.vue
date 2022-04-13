<template>
  <div>
    Filter Todos:
    <select v-model="selected">
      <option value="200">200</option>
      <option value="100">100</option>
      <option value="50">50</option>
      <option value="20">20</option>
      <option value="10">10</option>
      <option value="5">5</option>
    </select>
    {{ selected }}
  </div>
</template>

<script>
export default {
  name: "FilterTodos",
  data() {
    return {
      selected: 200,
    };
  },
  watch: {
    selected() {
      this.$store.dispatch("filterTodos", { selected: this.selected });
    },
  },
};
</script>

<style scoped>
select {
  margin-top: 20px;
  padding: 6px;
  border: 1px solid #41b883;
}
</style>