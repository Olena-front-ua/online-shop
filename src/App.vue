<template>
  <div id="app">
    <EmailPassword />
    <IncrementDecrement />
  </div>
</template>

<script>
import EmailPassword from "./components/EmailPassword.vue";
import IncrementDecrement from "./components/IncrementDecrement.vue";

export default {
  name: "App",
  components: {
    EmailPassword,
    IncrementDecrement,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
