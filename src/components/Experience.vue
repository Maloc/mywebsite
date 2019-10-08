<template>
  <v-container>
    <v-layout
      text-center
      wrap
    >
      <v-flex mb-4>
        <v-card-text style="margin-top: 50px;">
          <v-icon size="44px">fas fa-toolbox</v-icon>
          <h1 class="display-2 font-weight-bold mb-3">
            Expériences / Formations
          </h1>
        </v-card-text>
        <v-timeline>
          <v-timeline-item
            v-for="(year, i) in years"
            :key="i"
            :color="year.color"
            small
          >
            <template v-slot:opposite>
              <span
                :class="`headline font-weight-bold`"
                v-text="year.year"
              ></span>
            </template>
            <v-card class="elevation-2">
              <v-card-title class="headline">Lorem ipsum</v-card-title>
              <v-card-text>
                {{ year.text }}
              </v-card-text>
            </v-card>
          </v-timeline-item>
        </v-timeline>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: 'Experience',
  data: () => ({
    years: [
        {
          color: '#1F7087',
          year: 'Septembre 2018',
          text: 'Lorem ipsum dolor sit amet',
          icon: ''
        },
        {
          color: '#1F8087',
          year: '2017-2018',
          text: 'Lorem ipsum dolor sit amet'
        },
        {
          color: '#1F9087',
          year: '2016',
          text: 'Lorem ipsum dolor sit amet',
          icon: ''
        }
      ],
  }),
};
</script>
