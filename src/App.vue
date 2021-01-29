<template>
  <div id="app">
    <navbar />
    <router-view />
    <Footer />
  </div>
</template>

<script>
import Footer from "@/components/Footer.vue";
import navbar from "@/components/navbar.vue";

export default {
  components: {
    Footer,
    navbar,
  },
};
</script>