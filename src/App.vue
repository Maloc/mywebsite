<template>
  <v-app>
    <v-app-bar
      elevate-on-scroll
      fixed
      color="transparent"
    >
      <v-toolbar-title>guil.hoarau@gmail.com</v-toolbar-title>

      <div class="flex-grow-1"></div>

      <v-toolbar-items>
        <v-btn href="#Accueil" text>Accueil</v-btn>
        <v-btn href="#Profile" text>Profile</v-btn>
        <v-btn href="#Article" text>Article</v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-parallax
      id="Accueil"
      src="https://cdn.vuetifyjs.com/images/parallax/material.jpg"
    >
      <div
        align="center"
        justify="center"
      >
        <h1 class="display-2 font-weight-thin mb-4">Lorem ipsum</h1>
        <h4 class="subheading">Lorem ipsum dolor sit amet</h4>
      </div>
    </v-parallax>
    <v-content>
      <Profile id="Profile"/>
      <Article id="Article"/>
      <Experience id="Experience"/>
    </v-content>
    <v-footer
      dark
      padless
    >
      <v-card
        flat
        tile
        class="lighten-1 white--text text-center"
      >
        <v-card-text>
          <v-btn
            v-for="(icon, index) in icons"
            :key="index"
            class="mx-4 white--text"
            icon
            :href="icon.link"
          >
            <v-icon size="24px">{{ icon.title }}</v-icon>
          </v-btn>
        </v-card-text>

        <v-card-text class="white--text pt-0">
          Phasellus feugiat arcu sapien, et iaculis ipsum elementum sit amet. Mauris cursus commodo interdum. Praesent ut risus eget metus luctus accumsan id ultrices nunc. Sed at orci sed massa consectetur dignissim a sit amet dui. Duis commodo vitae velit et faucibus. Morbi vehicula lacinia malesuada. Nulla placerat augue vel ipsum ultrices, cursus iaculis dui sollicitudin. Vestibulum eu ipsum vel diam elementum tempor vel ut orci. Orci varius natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
        </v-card-text>

        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Guillaume Hoarau</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
import Profile from './components/Profile';
import Article from './components/Article';
import Experience from './components/Experience';

export default {
  name: 'App',
  components: {
    Profile,
    Article,
    Experience,
  },
  data: () => ({
    icons: [
      { title: 'fab fa-medium',
        link: 'https://medium.com/@ghoarau' },
      { title: 'fab fa-linkedin',
        link: 'https://www.linkedin.com/in/guillaume-hoarau-1636a4b6/' },
      { title: 'fab fa-github',
        link: 'https://github.com/Maloc' }
    ]
  })
};
</script>

<style scoped>
  .v-app-bar.v-app-bar--is-scrolled {
    background-color: #424242 !important;
  }
</style>
