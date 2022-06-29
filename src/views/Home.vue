<template>
  <div class="Home" id="home">
    <Navbar color="green lighten-1" textColor="white--text" btnColor="white" />
    <Cta />
    <About />
    <Services />
    <Footer />
  </div>
</template>

<script>
import Navbar from "../components/Navbar";
import Cta from "../components/Cta";
import About from "../components/About";
import Footer from "../components/Footer";
import Services from "../components/Services.vue";

export default {
  name: "Home",
  components: { Cta, About, Footer, Navbar, Services },
  data() {
    return {
      color: "transparent",
      item_color: "white",
    };
  },
};
</script>
