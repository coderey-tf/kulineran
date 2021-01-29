<template>
  <div class="hero">
    <!-- Desktop -->
    <div class="d-md-block d-none">
      <div class="row mt-5">
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong> Delicious Food menu</strong>, <br />in your gadget
              </h2>
              <p>Ayo segera pesan dan pilih makanan favoritmu!</p>
              <router-link to="/Foods" class="btn btn-lg btn-success"
                >Pesan</router-link
              >
            </div>
          </div>
        </div>
        <div class="col-md-6">
          <img src="../assets/img/hero.png" width="100%" />
        </div>
      </div>
    </div>

    <!-- Mobile -->
    <div class="d-sm-block d-md-none">
      <div class="row mt-5">
        <div class="col-md-6">
          <img src="../assets/img/hero.png" width="100%" />
        </div>
        <div class="col-md-6">
          <div class="d-flex h-100">
            <div class="justify-content-center align-self-center">
              <h2>
                <strong> Delicious Food menu</strong>, <br />in your gadget
              </h2>
              <p>Ayo segera pesan dan pilih makanan favoritmu!</p>
              <router-link to="/Foods" class="btn btn-lg btn-success"
                >Pesan</router-link
              >
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "hero",
};
</script>

<style>
</style>