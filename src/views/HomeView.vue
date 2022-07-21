<template>
  <div class="home">
    <v-toolbar flat>
      <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->
      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>
      <v-spacer></v-spacer>
      <v-toolbar-title>Narto</v-toolbar-title>
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

      <v-row class="px-3">
        <v-btn outlined class="mr-auto">Detil Stasiun</v-btn>
        <v-btn color="primary">Arahkan</v-btn>
      </v-row>

      <v-row class="px-3">
        <div class="text-h5 mr-auto">Fasilitas</div>
        <div class="text-h5">Lihat Semua ></div>
      </v-row>

      <v-row class="px-3">
        <RecycleScroller
          class="scroller"
          direction="horizontal"
          :itemSize="140"
          :items="facilities"
          key-field="name"
          v-slot="{ index }"
        >
          <!-- <HelloWorld :facilities="facility" /> -->
          <!-- <div v-for="facility in facilities" :key="facility.id"> -->
          <FacilityCard
            ref="childs"
            @wasClicked="testClick(facilities[index].id)"
            :facilities="facilities[index]"
          />
          <!-- </div> -->
        </RecycleScroller>
      </v-row>
    </v-container>

    <BottomNavigation />
  </div>
</template>

<script>
import BottomNavigation from "../components/BottomNavigation.vue";

import Vue from "vue";
import VueVirtualScroller from "vue-virtual-scroller";
import "vue-virtual-scroller/dist/vue-virtual-scroller.css";
// import HelloWorld from "@/components/HelloWorld.vue";

Vue.use(VueVirtualScroller);

export default {
  data: function () {
    return {
      facilities: [
        {
          id: "001",
          name: "Alfamart",
        },
        {
          id: "002",
          name: "bakso",
        },
        {
          id: "003",
          name: "roti 'o",
        },
        {
          id: "004",
          name: "Indomaret",
        },
        {
          id: "005",
          name: "tahu telor",
        },
      ],
    };
  },
  components: {
    BottomNavigation,
    FacilityCard: () => import("../components/FacilityCard.vue"),
    // HelloWorld,
  },
  methods: {
    testClick(id) {
      console.log(id);
    },
  },
};
</script>

<style scoped>
.scroller {
  height: 200px;
  margin-bottom: -100px;
}

.user {
  height: 32%;
  padding: 0 12px;
  display: flex;
  align-items: center;
}
</style>
