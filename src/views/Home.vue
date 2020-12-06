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
        <v-col xl="2" color="" class="d-flex align-center justify-end">
          <!-- <v-icon color="dark-grey">mdi-account</v-icon> -->
          <v-btn color="purple lighten-3 white--text mr-5">Login</v-btn>
          <v-btn color="purple lighten-2 white--text">Sign Up</v-btn>
        </v-col>
        <v-col cols="1"></v-col>
      </v-row>
    </div>

    <v-row class="my-0">
      <v-col cols="" sm="" md="" lg="7" xl="7" class="d-flex align-center">
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
          <v-col class=""><v-icon>mdi-copyright</v-icon> 2020 Travl </v-col>
        </v-row>
      </v-col>
      <v-col
        :style="scrollable" cols="" sm="" md="" lg="3"
        xl="2"
        class="d-flex flex-column justify-space-between scrollable"
      >
        <div v-for="image in images" :key="image.i" class="d-flex scroll">
          <v-img :src="`${image.img}`" contain class="scroll__img" />
          <v-card height="200" width="300" class="scrollable__card d-flex justify-center align-center">
            <v-img :src="`${image.cardImg}`" width="25%" class="card__img" />
            <div>
              <p class="headline">{{ image.cardText }}</p>
            </div>
          </v-card>
        </div>
      </v-col>
      <v-col cols="" sm="" md="" lg="2" xl="3" class="d-flex flex-column justify-center">
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
  data() {
    return {
      images: [
        {
          img:
            "https://www.shareicon.net/data/2016/08/24/820079_calendar_512x512.png",
          cardText: "Card text",
          cardImg:
            "https://www.shareicon.net/data/2016/08/24/820079_calendar_512x512.png",
        },
        {
          img:
            "https://www.shareicon.net/data/512x512/2016/08/31/821556_suitcase_512x512.png",
          cardText: "Card text",
          cardImg:
            "https://www.shareicon.net/data/512x512/2016/08/31/821556_suitcase_512x512.png",
        },
        {
          img:
            "http://www.pngall.com/wp-content/uploads/2/Travel-PNG-File-Download-Free.png",
          cardText: "Card text",
          cardImg:
            "http://www.pngall.com/wp-content/uploads/2/Travel-PNG-File-Download-Free.png",
        },
      ],
    };
  },
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

.scrollable {
  // height: 150vh!important;
}

.scroll {
  position: relative;
}

.scrollable__card {
  position: absolute;
  left: -100%;
  border-radius: 40px!important;
  top: 50%;
  margin-top: -25%;

  .card__img {
    position: absolute;
    top: -50px;
    border-radius: 0!important;
    left: 10px;
  }
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
