<template>
  <v-container fluid :style="home" class="home py-0 px-0">
    <div class="home__nav__container">
      <v-row class="home__nav px-0">
        <v-col cols="1"></v-col>
        <v-col xl="2" class="d-flex align-center justify-space-between px-0">
          <v-img src="https://i.imgur.com/a8JzMHo.png" class="nav__logo" />
        </v-col>
        <v-col xl="4" class="d-flex align-center">
          <router-link class="home__nav__btns px-3" to="/">home</router-link>
          <router-link class="home__nav__btns px-3" to="/features"
            >features</router-link
          >
          <router-link class="home__nav__btns px-3" to="/about"
            >about</router-link
          >
        </v-col>
        <v-col xl="2" class=""></v-col>
        <v-col xl="2" color="" class="d-flex align-center justify-space-around">
          <!-- <v-icon color="dark-grey">mdi-account</v-icon> -->
          <v-btn color="purple lighten-3 white--text">Login</v-btn>
          <v-btn color="purple lighten-2 white--text">Sign Up</v-btn>
        </v-col>
        <v-col cols="1"></v-col>
      </v-row>
    </div>

    <v-row class="my-0">
      <v-col xl="7" class="d-flex align-center">
        <v-row>
          <v-col cols="6" class="d-flex flex-column align-center mx-auto">
            <h1 class="display-2 home__heading">
              The best place to plan your trips and find the best the world has
              to offer
            </h1>
            <!-- <v-btn rounded color="yellow darken-2">Sign up<v-icon right>mdi-chevron-right</v-icon></v-btn> -->
          </v-col>
        </v-row>
        <v-row>
          <v-col class="d-flex">
            <v-icon>mdi-copyright</v-icon> 2020 Travl
          </v-col>
        </v-row>
      </v-col>
      <v-col :style="scrollable" xl="2"></v-col>
      <v-col xl="3" class="d-flex flex-column justify-center">
        <v-btn fab class="my-10" color="purple lighten-3"
          ><v-icon>mdi-chevron-up</v-icon></v-btn
        >
        <v-btn fab class="my-10" color="purple lighten-3"
          ><v-icon>mdi-chevron-down</v-icon></v-btn
        >
        <!-- <v-btn fab class="my-10" color="yellow darken-2"><v-icon>mdi-chevron-down</v-icon></v-btn> -->
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
  computed: {
    home() {
      return {
        "background-color": this.$store.state.primaryColor,
      };
    },
    scrollable() {
      return {
        "background-color": this.$store.state.secondaryColor,
        height: "100vh",
      };
    },
  },
};
</script>

<style lang="scss" scoped>
.home {
  height: 100vh;

  .home__heading {
    line-height: 80px;
  }
}

.nav__logo {
  max-width: 70px;
}

.home__nav__container {
  position: absolute;
  top: 70px;
  width: 100vw;
}

.home__nav {
  width: 100%;
  .home__nav__btns {
    list-style: none;
    text-decoration: none;
    color: rgb(44, 44, 44);
  }
}
</style>
