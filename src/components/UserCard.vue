<template>
  <div>
    <h1></h1>
    <div>
      <!--      <img src="../assets/images/logo.png" width="300px" />-->
      <div>
        <h2>
          {{ getAuthorFullName }}
        </h2>
        <strong></strong>
        <ul>
          <li></li>
          <li></li>
          <li></li>
        </ul>
      </div>
    </div>
    <p>Кількість учасників: {{ users.length }}</p>
    <ul>
      <li v-for="(user, index) in users" :key="index">
        {{ `${index + 1} ${getFullName(user)}` }}
      </li>
    </ul>
    <button type="button" @click="currentPage--">Prev</button>
    <button
      v-for="page in pages"
      :key="page"
      type="button"
      @click="currentPage = page"
    >
      {{ page }}
    </button>
    <button type="button" @click="currentPage++">Next</button>
    <p>Pade {{ currentPage }} of {{ pages }}</p>
  </div>
</template>
<script>
export default {
  name: "userCard",
  data() {
    return {
      firstName: "G",
      secondName: "k",
      lastName: "L",
      users: [
        {
          firstName: "Olena",
          secondName: "Vasylchuk",
          lastName: "Vadymivna",
        },
        {
          firstName: "xfgnh",
          secondName: "fdxn",
          lastName: "tjnfr",
        },
        {
          firstName: "sretjhn",
          secondName: "nrth",
          lastName: "trjhsrtghsa",
        },
      ],
      pages: 3,
      currentPage: 1,
    };
  },
  computed: {
    getAuthorFullName() {
      return `${this.firstName}
      ${this.lastName} ${this.secondName.toUpperCase()}`;
    },
  },
  methods: {
    getFullName(user) {
      return `${user.firstName}
      ${user.lastName} ${user.secondName.toUpperCase()}`;
    },
    loadUsers(page) {
      console.log(`Load users: page ${page}`);
    },
  },
  watch: {
    currentPage(page) {
      this.loadUsers(page);
    },
  },
};
</script>
