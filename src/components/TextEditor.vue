<template>
  <div class="text-editor">
    <textarea v-model="text"></textarea>
    <div class="output-text" :inner-html.prop="text | upperCase | emoji"></div>
    <!--    <div class="output-text" :inner-html.prop="text | marked"></div>-->
  </div>
</template>

<script>
export default {
  name: "TextEditor",
  data() {
    return {
      text: "",
    };
  },
  filters: {
    upperCase(value) {
      return value.toUpperCase();
    },
    emoji(value) {
      return value.replace(":)", "😀");
    },
  },
};
</script>

<style scoped>
textarea {
  width: 500px;
  height: 200px;
}
</style>
