<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <v-card-text style="margin-top: 50px; margin-bottom: 50px;">
          <v-icon size="44px">far fa-newspaper</v-icon>
          <h1 class="display-2 font-weight-bold mb-3">
            Articles
          </h1>
        </v-card-text>
        <v-col
          v-for="(item, i) in items"
          :key="i"
        >
          <v-card
            :color="item.color"
            dark
          >
            <v-list-item :href="item.link" three-line>
              <v-list-item-avatar
                size="125"
                tile
              >
                <v-img :src="item.src"></v-img>
              </v-list-item-avatar>
              <v-list-item-content>
                <v-list-item-title
                  class="headline mb-2"
                  v-text="item.title"
                ></v-list-item-title>

                <v-list-item-subtitle v-text="item.published"></v-list-item-subtitle>
                <v-list-item-subtitle v-text="item.sumup"></v-list-item-subtitle>
              </v-list-item-content>

              <v-chip outlined>{{ item.chips[0] }}</v-chip>
              <v-chip outlined>{{ item.chips[1] }}</v-chip>
              <v-chip outlined>{{ item.chips[2] }}</v-chip>
            </v-list-item>
          </v-card>
        </v-col>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Article',
  data: () => ({
    items: [
        {
          color: '#1F7087',
          src: 'https://cdn.vuetifyjs.com/images/cards/foster.jpg',
          title: 'Lorem',
          sumup: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          published: '2018-10-23',
          chips: ['Lorem', 'Ipsum', 'Dolor'],
          link: "https://medium.com/futurs-io/quel-langage-utiliser-pour-votre-back-end-cb915a053ccc"
        },
        {
          color: '#1F8087',
          src: 'https://cdn.vuetifyjs.com/images/cards/halcyon.png',
          title: 'Ipsum',
          sumup: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
          published: '2018-10-23',
          chips: ['Lorem', 'Ipsum', 'Dolor'],
          link: "https://medium.com/futurs-io/quel-langage-utiliser-pour-votre-back-end-cb915a053ccc"
        },
      ],
  }),
};
</script>
