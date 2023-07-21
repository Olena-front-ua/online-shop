<template>
  <input
    type="text"
    class="search"
    @input="$emit('input', $event.target.value)"
  />
</template>

<script>
export default {
  model: {
    prop: "vale",
    event: "input",
  },
};
</script>

<script setup></script>
