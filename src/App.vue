<template>
  <div id="app">
    <EmailPassword />
    <span>___________________________________________-</span>
    <IncrementDecrement />
    <span>___________________________________________-</span>
    <UserCard />
    <span>___________________________________________-</span>
    <SearchByName />
    <span>___________________________________________-</span>
  </div>
</template>

<script>
import EmailPassword from "./components/EmailPassword.vue";
import IncrementDecrement from "./components/IncrementDecrement.vue";
import UserCard from "@/components/UserCard.vue";
import SearchByName from "@/components/SearchByName.vue";

export default {
  name: "App",
  components: {
    SearchByName,
    UserCard,
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
