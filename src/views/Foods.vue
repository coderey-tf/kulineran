<template>
  <div>
    <div class="container mt-5">
      <h2>Daftar <strong>Makanan</strong></h2>

      <div class="input-group mt-3 mb-2">
        <input
          v-model="search"
          type="text"
          class="form-control"
          placeholder="Cari Makanan Kesukaanmu"
          aria-label="Cari"
          aria-describedby="basic-addon1"
          @keyup="searchFoods"
        />
        <span class="input-group-text" id="basic-addon1"
          ><b-icon-search></b-icon-search
        ></span>
      </div>
      <div class="row mb-3">
        <div
          class="col-md-4 mt-3"
          v-for="product in products"
          :key="product.id"
        >
          <CardProduct :product="product" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import axios from "axios";
import CardProduct from "@/components/CardProduct.vue";

export default {
  name: "Foods",
  components: {
    CardProduct,
  },
  data() {
    return {
      products: [],
      search: "",
    };
  },
  methods: {
    setProducts(data) {
      this.products = data;
    },
    searchFoods() {
      axios
        .get("http://localhost:3000/products?q=" + this.search)
        .then((response) => this.setProducts(response.data))

        .catch((error) => console.log(error));
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products")
      .then((response) => this.setProducts(response.data))

      .catch((error) => console.log(error));
  },
};
</script>