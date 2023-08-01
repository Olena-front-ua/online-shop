<template>
  <form class="sign-up" @submit.prevent="checkForm">
    <div class="form-group">
      <label for="login">Логін:</label>
      <input
        id="login"
        class="form-control"
        :class="$v.form.login.$error ? 'is-invalid' : ''"
        v-model.trim="form.login"
      />
      <p
        v-if="$v.form.login.$dirty && !$v.form.login.required"
        class="invalid-feedback"
      >
        Обов'язкове поле
      </p>
      <p
        v-if="$v.form.login.$dirty && !$v.form.login.minLength"
        class="invalid-feedback"
      >
        Тут повинно бути більше 5-ти символів
      </p>
    </div>
    <div class="form-group">
      <label for="login">Почта:</label>
      <input
        id="email"
        type="email"
        class="form-control"
        :class="$v.form.email.$error ? 'is-invalid' : ''"
        v-model.trim="form.email"
      />
      <p
        v-if="$v.form.login.$dirty && !$v.form.email.required"
        class="invalid-feedback"
      >
        Обов'язкове поле
      </p>
      <p
        v-if="$v.form.login.$dirty && !$v.form.email.email"
        class="invalid-feedback"
      >
        Email некоректний
      </p>
    </div>
    <div class="form-group">
      <label for="login">Пароль:</label>
      <input
        id="password"
        type="password"
        class="form-control"
        :class="$v.form.password.$error ? 'is-invalid' : ''"
        v-model.trim="form.password"
      />
      <p
        v-if="$v.form.login.$dirty && !$v.form.password.required"
        class="invalid-feedback"
      >
        Обов'язкове поле
      </p>
    </div>
    <div class="form-group">
      <label for="country">Країна проживання:</label>
      <select id="country" class="form-control" v-model="form.country">
        <option
          v-for="(country, index) in countries"
          :value="country.value"
          :key="index"
        >
          {{ country.label }}
        </option>
      </select>
    </div>
    <div class="form-group">
      <label for="themes">Улюблені теми:</label>
      <select
        id="themes"
        class="form-control"
        v-model="form.favoriteThemes"
        multiple
      >
        <option
          v-for="(theme, index) in themes"
          :value="theme.value"
          :key="index"
        >
          {{ theme.label }}
        </option>
      </select>
    </div>
    <div class="form-group form-check">
      <input
        type="checkbox"
        class="form-check-input"
        id="notification"
        v-model="form.agreeWithSendEmail"
      />
      <label class="form-check-label" for="notification">
        Повідоляти мене про нові курси
      </label>
    </div>
    <div class="form-group form-check">
      <input
        type="checkbox"
        class="form-check-input"
        id="rules"
        :class="$v.form.rules.$error ? 'is-invalid' : ''"
        v-model.trim="form.rules"
      />
      <label class="form-check-label" for="notification">
        Ознайомлена з правилами
      </label>
      <p
        v-if="$v.form.login.$dirty && !$v.form.password.required"
        class="invalid-feedback"
      >
        Обов'язкове поле
      </p>
    </div>
    <div class="flex">
      <div class="form-check">
        <input
          class="form-check-input"
          type="radio"
          value="male"
          name="exampleRadios"
          id="male"
          v-model="form.gender"
        />
        <label class="form-check-label" for="male"> Чоловік </label>
      </div>
      <div class="form-check">
        <input
          class="form-check-input"
          type="radio"
          value="female"
          name="exampleRadios"
          id="female"
          v-model="form.gender"
        />
        <label class="form-check-label" for="female"> Жінка </label>
      </div>
    </div>
    <button type="submit" class="btn btn-primary">Відправити</button>
  </form>
</template>

<script>
import { validationMixin } from "vuelidate";
import { required, minLength, email } from "vuelidate/lib/validators";

export default {
  mixins: [validationMixin],
  data() {
    return {
      form: {
        login: "",
        email: "",
        password: "",
        country: "Russia",
        favoriteThemes: ["IT"],
        agreeWithSendEmail: false,
        rules: false,
        gender: "male",
      },
      countries: [
        {
          label: "Польща",
          value: "Poland",
        },
        {
          label: "Україна",
          value: "Ukraine",
        },
        {
          label: "США",
          value: "USA",
        },
      ],
      themes: [
        {
          label: "Технології",
          value: "IT",
        },
        {
          label: "Мови",
          value: "languages",
        },
        {
          label: "Математика",
          value: "mathematics",
        },
      ],
    };
  },
  validations: {
    form: {
      login: { required, minLength: minLength(5) },
      email: { required, email },
      password: { required },
      rules: { required },
    },
  },
  methods: {
    checkForm() {
      this.$v.form.$touch();
      if (!this.$v.form.$error) {
        console.log("Валидация прошла успешно");
      }
    },
  },
};
</script>

<style scoped>
.form-control {
  width: 400px;
}
.form-check {
  margin-right: 10px;
}
button {
  margin-top: 15px;
}
</style>
