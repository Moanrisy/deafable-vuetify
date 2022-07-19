<template>
  <div class="home">
    <v-toolbar>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>
      <v-toolbar-title>Title</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>

    <v-container>
      <div class="text-h5">Stasiun Terdekat</div>
      <v-row class="mb-0 mt-1">
        <v-col cols="4">
          <v-img
            style="border-radius: 12px"
            height="200"
            width="130"
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
          >
          </v-img>
        </v-col>
        <v-col cols="8">
          <v-card flat>
            <v-card-title class="pa-0">Stasiun Rawa Buntu</v-card-title>
            <div class="text-body-2">13.20 | (1.2 Km dari anda)</div>
            <div class="text-body-2 green--text font-weight-bold">
              Jalur Hijau
            </div>

            <v-timeline dense class="ml-n10">
              <v-timeline-item color="green" small class="my-n4">
                <v-row class="pt-1">
                  <v-col>
                    <div class="text-caption">Mobile App</div>
                  </v-col>
                </v-row>
              </v-timeline-item>
              <v-timeline-item color="green" small class="my-n4">
                <v-row class="pt-1">
                  <v-col>
                    <strong>New Icon</strong>
                  </v-col>
                </v-row>
              </v-timeline-item>
              <v-timeline-item color="green" small>
                <v-row class="pt-1">
                  <v-col>
                    <div class="text-caption">Mobile App (S. Transit)</div>
                  </v-col>
                </v-row>
              </v-timeline-item>
            </v-timeline>
          </v-card>
        </v-col>
      </v-row>

      <v-row>
        <v-btn outlined class="mr-auto">Detil Stasiun</v-btn>
        <v-btn color="primary">Arahkan</v-btn>
      </v-row>

      <v-row class="px-3">
        <div class="text-h5 mr-auto">Fasilitas</div>
        <div class="text-h5">Lihat Semua ></div>
      </v-row>
      <v-row>
        <v-card class="ml-4">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="200px"
            width="130px"
            style="border-radius: 12px"
          >
            <v-card-title>Indomaret</v-card-title>
            <v-card-subtitle>08.00 - 22.00</v-card-subtitle>
          </v-img>
        </v-card>
        <v-card class="ml-4">
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="200px"
            width="130px"
            style="border-radius: 12px"
          >
            <v-card-title>Roti 'O</v-card-title>
            <v-card-subtitle>08.00 - 23.00</v-card-subtitle>
          </v-img>
        </v-card>
      </v-row>
    </v-container>

    <BottomNavigation />
  </div>
</template>

<script>
import BottomNavigation from "../components/BottomNavigation.vue";

export default {
  components: {
    BottomNavigation,
  },
};
</script>
