<template>
  <div>
    <MyInput v-model="searchText" />
    <p>All names: {{ names.length }}, matches: {{ getFilteredNames.length }}</p>
    <ul>
      <li v-for="(name, index) in getFilteredNames" :key="index">
        {{ name }}
      </li>
    </ul>
  </div>
</template>

<script>
import MyInput from "@/components/Search/MyInput.vue";

export default {
  name: "searchByName",
  components: { MyInput },
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
