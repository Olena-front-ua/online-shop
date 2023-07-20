<template>
  <div>
    <input type="text" @input="searchText = $event.target.value" />
    <p>All names: {{ names.length }}, matches: {{ getFilteredNames.length }}</p>
    <ul>
      <li v-for="(name, index) in getFilteredNames" :key="index">
        {{ name }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "searchByName",
  data() {
    return {
      searchText: " ",
      names: ["Kira", "Zara", "Mila", "Helen", "Mark", "Philip", "Jack"],
    };
  },
  computed: {
    getFilteredNames() {
      return this.names.filter((name) =>
        name.toLowerCase().includes(this.searchText.toLowerCase())
      );
    },
  },
};
</script>

<style></style>
