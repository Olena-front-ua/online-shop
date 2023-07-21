<template>
  <div class="product-card">
    <img :src="imgUrl" width="300px" alt="Product img" />
    <div>
      <h2>{{ title }}</h2>
      <p>{{ price }}</p>
      <p>Доступно для доставки {{ count }} шт.</p>
      <button type="button" @click="addToCart">Add to cart</button>
    </div>
  </div>
</template>
<script>
export default {
  name: "productCard",
  props: {
    imgUrl: {
      type: String,
      default:
        "https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.puriindahmall.co.id%2Fassets%2Fimg%2F%3FSA&psig=AOvVaw0Y_BsOCx7r4FOVLiRXFun0&ust=1690009628440000&source=images&cd=vfe&opi=89978449&ved=0CBEQjRxqFwoTCNil_tSen4ADFQAAAAAdAAAAABAD",
    },
    title: {
      type: String,
      validator(value) {
        return value.length < 50;
      },
    },
    price: {
      type: Number,
      required: true,
    },
    count: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {};
  },
  methods: {
    addToCart() {
      this.$emit("addToCart");
    },
  },
};
</script>
