<template>
  <div>
    <EmailPassword />
    <span>___________________________________________-</span>
    <IncrementDecrement />
    <span>___________________________________________-</span>
    <UserCard />
    <span>___________________________________________-</span>
    <SearchByName />
    <span>___________________________________________-</span>
    <Filters />
    <span>___________________________________________-</span>
    <ProductList />
    <span>___________________________________________-</span>
    <ReactivityForm />
    <span>___________________________________________-</span>
  </div>
</template>

<script>
import EmailPassword from "@/components/EmailPassword.vue";
import IncrementDecrement from "@/components/IncrementDecrement.vue";
import UserCard from "@/components/UserCard.vue";
import SearchByName from "@/components/SearchByName.vue";
import Filters from "@/components/Filters.vue";
import ProductList from "@/components/Product/ProductList.vue";
import ReactivityForm from "@/components/Reactivity.vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "home",
  components: {
    ReactivityForm,
    ProductList,
    Filters,
    SearchByName,
    UserCard,
    EmailPassword,
    IncrementDecrement,
  },
};
</script>
