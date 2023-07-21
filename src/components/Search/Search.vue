<template>
  <div>
    <input type="text" class="search" v-model="searchText" />
    <button type="button" @click="$emit('search', searchText)">Search</button>
  </div>
</template>

<script>
export default {
  name: "searchComponent",
  data() {
    return {
      searchText: "",
    };
  },
};
</script>
