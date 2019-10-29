<template>
  <v-container
    style="margin-bottom: 50px;"
  >
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <v-card-text style="margin-top: 50px;">
          <v-icon size="44px">far fa-newspaper</v-icon>
          <h1 class="display-2 font-weight-bold mb-3">
            {{ $t('title.2.title') }}
          </h1>
        </v-card-text>
        <v-col
          v-for="(item, i) in $t('news')"
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
    //
  }),
};
</script>
