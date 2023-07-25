<template>
  <div>
    <h2>Reactivity</h2>
    <div>
      <div>
        <h2>About me:</h2>
        <div v-for="(fieldValue, fieldLabel, index) in formFields" :key="index">
          <label :for="fieldLabel">{{ fieldLabel }}</label>
          <input id="fieldLabel" v-model="formFields[fieldLabel]" />
        </div>
        <button type="submit">Save</button>
      </div>
      <div>
        <h2>Preview</h2>
        <p v-for="(fieldValue, fieldLabel, index) in formFields" :key="index">
          {{ `${fieldLabel}: ${fieldValue}` }}
        </p>
      </div>
    </div>
    <div>
      <label for="additionalField">Additional field</label>
      <input id="additionalField" v-model="additionalField" />
      <button type="button" @click="addNewField">Add</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "ReactivityForm",
  data() {
    return {
      formFields: {
        firstName: "",
        secondName: "",
        lastName: "",
      },
      additionalField: "",
    };
  },
  methods: {
    addNewField() {
      this.$set(this.formFields, this.additionalField, "");
    },
  },
};
</script>
