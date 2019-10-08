<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <v-card-text style="margin-top: 50px;">
          <v-icon size="44px">far fa-address-card</v-icon>
          <h1 class="display-2 font-weight-bold mb-3">
            Contact
          </h1>
        </v-card-text>
        <p class="subheading font-weight-regular">
          <v-icon>far fa-paper-plane</v-icon>
          <a href="mailto:guil.hoarau@gmail.com">guil.hoarau@gmail.com</a>
        </p>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Contact',
  data: () => ({
    //
  }),
};
</script>
