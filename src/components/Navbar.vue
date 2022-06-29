<template>
  <div class="Home">
    <v-app-bar
      :color="color"
      flat
      fixed
      elevation="0"
      height="70"
      class="navbar"
      :class="{ 'navbar-container': this.$vuetify.breakpoint.xl }"
    >
      <div class="pl-10 text-h6 text-md-h4">
        <v-icon :class="textColor"> mdi-earth </v-icon>
        <span class="white--text"> 3D </span>
        <span :class="textColor">Earth</span>
      </div>
      <v-spacer></v-spacer>
      <!-- NAV-MENU -->
      <div class="nav d-flex" v-if="this.$vuetify.breakpoint.mdAndUp">
        <div class="nav-content" v-for="(link, i) in navLinks" :key="i">
          <router-link v-if="link.routerLink" :to="link.to">
            <v-btn text tile :color="btnColor">
              {{ link.text }}
            </v-btn>
          </router-link>
          <a v-else>
            <v-btn text tile :color="btnColor" @click="$vuetify.goTo(link.to)">
              {{ link.text }}
            </v-btn>
          </a>
        </div>
      </div>

      <!-- MOBILE-NAV-MENU -->
      <div class="mobile-nav" v-else>
        <v-app-bar-nav-icon color="white" @click="drawer = !drawer">
        </v-app-bar-nav-icon>
      </div>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      fixed
      color="white"
      height="100vh"
      width="50%"
    >
      <v-list class="d-flex flex-column justify-center align-center">
        <v-list-item v-for="(link, i) in navLinks" :key="i">
          <router-link :to="link.to" v-if="link.routerLink">
            <v-btn text tile>
              {{ link.text }}
            </v-btn>
          </router-link>
          <a v-else>
            <v-btn text tile @click="$vuetify.goTo(link.to), (drawer = false)">
              {{ link.text }}
            </v-btn>
          </a>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props: {
    color: {
      type: String,
    },
    btnColor: {
      type: String,
    },
    textColor: {
      type: String,
    },
  },
  data() {
    return {
      navLinks: [
        { text: "Inicio", to: "#home", routerLink: false },
        { text: "Sobre Nosotros", to: "#about", routerLink: false },
        { text: "Servicios", to: "#services", routerLink: false },
      ],
      drawer: false,
    };
  },
  methods: {},

  beforeMount() {
    window.addEventListener("scroll", this.changeColor);
  },
};
</script>

<style scoped lang="scss">
.navbar-container {
  padding: 0 5rem;
}
.change-color {
  background-color: white;
}
</style>
