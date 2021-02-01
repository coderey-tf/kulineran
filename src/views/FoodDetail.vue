<template>
  <div class="container">
    <!-- breadcrumb -->
    <div class="row">
      <div class="col">
        <nav aria-label="breadcrumb">
          <ol class="breadcrumb">
            <li class="breadcrumb-item">
              <router-link to="/" class="text-dark">Home</router-link>
            </li>
            <li class="breadcrumb-item">
              <router-link to="/Foods" class="text-dark">Foods</router-link>
            </li>
            <li class="breadcrumb-item active" aria-current="page">
              Food Order
            </li>
          </ol>
        </nav>
      </div>
    </div>

    <div class="row">
      <div class="col-md-6">
        <img
          :src="'../assets/img/' + product.gambar"
          class="img-fluid shadow"
          alt="..."
        />
      </div>
      <div class="col-md-6">
        <h2>
          <strong>{{ product.nama }}</strong>
        </h2>
        <hr />
        <h4>
          Harga : <strong>Rp. {{ product.harga }} </strong>
        </h4>
        <div class="form-group mt-3">
          <label for="jumlah_pemesanan">Jumlah Pesan</label>
          <input type="number" class="form-control" placeholder="1,2,3, etc." />
        </div>
        <div class="form-group">
          <label for="keterangan">Keterangan</label>
          <textarea
            class="form-control"
            placeholder="Contoh : pedes, manis, etc"
          ></textarea>
        </div>
        <button type="submit" class="btn btn-success">
          <b-icon-cart></b-icon-cart>Pesan
        </button>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "FoodDetail",
  data() {
    return {
      product: [],
    };
  },
  methods: {
    setProduct(data) {
      this.product = data;
    },
  },
  mounted() {
    axios
      .get("http://localhost:3000/products/" + this.$route.params.id)
      .then((response) => this.setProduct(response.data))

      .catch((error) => console.log(error));
  },
};
</script>

<style>
</style>