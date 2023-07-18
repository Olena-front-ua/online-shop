<template>
  <div>
    <label>
      {{ label }}
      <br />
      <button @click="incrementItem">+</button>
      <p>{{ counter }}</p>
      <button @click="decrementItem">-</button>
    </label>
  </div>
</template>

<script>
export default {
  name: "IncrementDecrement",
  data() {
    return {
      label: "Select the number of products:",
      counter: 0,
      maxNumber: 10,
    };
  },
  methods: {
    incrementItem() {
      if (this.counter < this.maxNumber) {
        this.counter++;
      }
    },
    decrementItem() {
      if (this.counter > 0) {
        this.counter--;
      }
    },
  },
};
</script>

<style scoped></style>
