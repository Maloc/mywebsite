<template>
  <v-app>
    <v-app-bar
      elevate-on-scroll
      fixed
      color="transparent"
      dark
    >

      <div class="flex-grow-1"></div>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn 
          v-for="(item, index) in menu"
          :key="index"
          :href="item.link" text>{{ item.title }}</v-btn>
      </v-toolbar-items>
      <v-menu class="hidden-md-and-up">
        <template v-slot:activator="{ on }">
          <v-btn
            dark
            icon
            v-on="on"
            class="hidden-md-and-up"
          >
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item
            v-for="(item, i) in menu"
            :key="i"
            :href="item.link"
          >
            <v-list-item-title>{{ item.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>
    <v-parallax
      id="Accueil"
      src="./assets/bg.jpeg"
      height="700"
    >
      <div
        align="center"
        justify="center"
      >
        <h1 class="display-2 font-weight-thin mb-4">Lorem ipsum</h1>
        <h4 class="subheading">Lorem ipsum dolor sit amet</h4>
        <v-btn
          color="blue-grey"
          class="ma-2 white--text"
        >
          CV en PDF
          <v-icon right dark>mdi-cloud-upload</v-icon>
        </v-btn>
      </div>
    </v-parallax>
    <v-content>
      <Profile id="Profile"/>
      <v-divider></v-divider>
      <Article id="Article"/>
      <v-divider></v-divider>
      <Experience id="Experience"/>
    </v-content>
    <v-footer
    dark
      padless
    >
      <v-card
        color="#022238"
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
    ],
    menu: [
      { title: 'Accueil', link: '#Accueil' },
      { title: 'Profil', link: '#Profile' },
      { title: 'Articles', link: '#Article' },
      { title: 'Expériences', link: '#Experience' }
      ]
  })
};
</script>

<style scoped>
  .v-app-bar.v-app-bar--is-scrolled {
    background-color: #022238!important;
  }
</style>
