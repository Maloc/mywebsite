<template>
  <v-app>
    <v-app-bar
      elevate-on-scroll
      fixed
      color="transparent"
      dark
    >
      <v-app-bar-nav-icon class="hidden-md-and-up" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
      <div class="flex-grow-1"></div>

      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn 
          v-for="(item, index) in menu"
          :key="index"
          :href="item.link" text>{{ item.title }}</v-btn>
      </v-toolbar-items>
      <v-toolbar-items>
        <v-menu offset-y>
          <template v-slot:activator="{ on }">
            <v-btn
              depressed
              color="transparent"
              v-on="on"
            >
              <flag :iso="currentLanguage" v-bind:squared=false />
            </v-btn>
          </template>
          <v-list>
            <v-list-item
              v-for="(language, index) in languages"
              :key="index"
            >
              <v-list-item-title>
                <button @click="changeLocale(language)">
                    <flag :iso="language.flag" v-bind:squared=false /> {{language.title}}
                </button>
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar-items>
    </v-app-bar>
    <v-navigation-drawer
      v-model="drawer"
      app
      temporary
    >
      <v-list nav dense>
        <v-list-item-group
          v-model="group"
          active-class="text--accent-4"
        >
            <v-list-item
              v-for="(item, i) in menu"
              :key="i"
              :href="item.link"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-parallax
      id="Accueil"
      src="./assets/bg.jpeg"
      height="700"
    >
      <div
        align="center"
        justify="center"
      >
        <h1 class="display-2 font-weight-thin mb-4">Guillaume Hoarau</h1>
        <h4 class="subheading">{{ $t('jobTitle') }}</h4>
        <v-btn
          color="blue-grey"
          class="ma-2 white--text"
        >
          {{ $t('cvButton') }}
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
      <v-divider></v-divider>
      <Contact id="Contact"/>
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
import Contact from './components/Contact';
import i18n from './i18n';

export default {
  name: 'App',
  components: {
    Profile,
    Article,
    Experience,
    Contact
  },
  data: () => ({
    drawer: false,
    group: null,
    currentLanguage: i18n.locale,
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
      { title: 'Expériences', link: '#Experience' },
      { title: 'Contact', link: '#Contact' }
    ],
    languages: [
      { flag: 'us', locale: 'en', title: 'English' },
      { flag: 'fr', locale: 'fr', title: 'French' }
    ]
  }),
  watch: {
    group () {
      this.drawer = false
    },
  },
  methods: {
    changeLocale(langage) {
      i18n.locale = langage.locale;
      this.currentLanguage = langage.flag;
    }
  }
};
</script>

<style scoped>
  .v-app-bar.v-app-bar--is-scrolled {
    background-color: #022238!important;
  }
</style>
