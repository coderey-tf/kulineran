<template>
  <div class="card shadow mb-5 bg-white card-product">
    <img
      :src="'../assets/img/' + product.gambar"
      class="card-img-top"
      alt="..."
      width="350"
      height="235"
    />
    <div class="card-body">
      <h5 class="card-title">{{ product.nama }}</h5>
      <p class="card-text">Harga : {{ product.harga }}</p>
      <a href="#" class="btn btn-success"
        ><b-icon-cart class="mr-2"></b-icon-cart>Pesan</a
      >
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"],
};
</script>

<style>
</style>  