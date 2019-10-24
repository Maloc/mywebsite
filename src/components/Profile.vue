<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <v-card-text style="margin-top: 50px; margin-bottom: 50px;">
          <v-icon size="44px">fas fa-users</v-icon>
          <h1 class="display-2 font-weight-bold mb-3">
            Profil
          </h1>
        </v-card-text>
        <p class="subheading font-weight-regular">
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum."
        </p>
      </v-flex>
      <v-row>
      <v-col
        v-for="n in 3"
        :key="n"
        cols="12"
        sm="4"
      >
        <v-card
          class="pa-2"
          tile
        >
          <h1 class="mb-3">
            {{me[n-1].title}}
          </h1>
            {{ me[n-1].content }}
        </v-card>
      </v-col>
    </v-row>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Profile',
  data: () => ({
    me : [
      {
        title: "Lorem",
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
      },
      {
        title: "ipsum",
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
      },
      {
        title: "dolor",
        content: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua."
      },
    ]
  }),
};
</script>
