<template>
  <div class="product-list">
    <div class="flex top-information">
      <Search @search="searchProducts" />
    </div>
    <ul class="list-default flex">
      <li v-for="(product, index) in getFilteredProducts" :key="index">
        <ProductCard
          :img-url="product.imgUrl"
          :title="product.title"
          :price="product.price"
          :count="product.count"
          @addToCart="addToCart(index)"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import ProductCard from "@/components/Product/ProductCard.vue";
import Search from "@/components/Search/Search.vue";

export default {
  name: "productList",
  components: { Search, ProductCard },
  data() {
    return {
      searchText: "",
      products: [
        {
          title: "Стіл Jim",
          price: 19999,
          imgUrl:
            "https://media.istockphoto.com/id/1047259374/uk/%D1%84%D0%BE%D1%82%D0%BE/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D1%83%D0%B2%D0%B0%D0%BD%D0%BD%D1%8F-%D0%B2%D0%B8%D1%85%D1%96%D0%B4%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BE%D0%B4%D1%83-%D0%B0%D0%B1%D1%81%D1%82%D1%80%D0%B0%D0%BA%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D1%84%D0%BE%D0%BD%D1%83.jpg?s=1024x1024&w=is&k=20&c=A-vMT43e_JV-29IQoBijr_tiDrUu5rLSafmiy0seQJ4=",
          count: 30,
        },
        {
          title: "Стіл Monako",
          price: 19090,
          imgUrl:
            "https://media.istockphoto.com/id/1047259374/uk/%D1%84%D0%BE%D1%82%D0%BE/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D1%83%D0%B2%D0%B0%D0%BD%D0%BD%D1%8F-%D0%B2%D0%B8%D1%85%D1%96%D0%B4%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BE%D0%B4%D1%83-%D0%B0%D0%B1%D1%81%D1%82%D1%80%D0%B0%D0%BA%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D1%84%D0%BE%D0%BD%D1%83.jpg?s=1024x1024&w=is&k=20&c=A-vMT43e_JV-29IQoBijr_tiDrUu5rLSafmiy0seQJ4=",
          count: 23,
        },
        {
          title: "Стіл з двома ящиками",
          price: 18546,
          imgUrl:
            "https://media.istockphoto.com/id/1047259374/uk/%D1%84%D0%BE%D1%82%D0%BE/%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D1%83%D0%B2%D0%B0%D0%BD%D0%BD%D1%8F-%D0%B2%D0%B8%D1%85%D1%96%D0%B4%D0%BD%D0%BE%D0%B3%D0%BE-%D0%BA%D0%BE%D0%B4%D1%83-%D0%B0%D0%B1%D1%81%D1%82%D1%80%D0%B0%D0%BA%D1%82%D0%BD%D0%BE%D0%B3%D0%BE-%D1%84%D0%BE%D0%BD%D1%83.jpg?s=1024x1024&w=is&k=20&c=A-vMT43e_JV-29IQoBijr_tiDrUu5rLSafmiy0seQJ4=",
          count: 20,
        },
      ],
    };
  },
  methods: {
    addToCart(index) {
      console.log(index);
    },
    searchProducts(searchText) {
      console.log("Завантажити товари: " + searchText);
      this.searchText = searchText;
    },
  },
  computed: {
    getFilteredProducts() {
      return this.products.filter((product) =>
        product.title.toLowerCase().includes(this.searchText.toLowerCase())
      );
    },
  },
};
</script>
