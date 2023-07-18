<template>
  <div>
    <div class="hello">{{ title }}</div>
    <label>
      E-mail:
      <input
        type="email"
        :value="email"
        @:input="emailInput($event.target.value)"
      />
    </label>
    <label>
      Password:
      <input
        type="password"
        :value="password"
        @:input="passwordInput($event.target.value)"
      />
      email: {{ email }} email: {{ password }}
    </label>
  </div>
</template>

<script>
export default {
  name: "EmailPassword",
  data() {
    return {
      title: "Hello",
      email: "olena.vasylchuk@vist-m.com",
      password: "sdhrfgvkdhbvk",
    };
  },
  methods: {
    emailInput(value) {
      this.email = value;
    },
    passwordInput(value) {
      this.password = value;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
