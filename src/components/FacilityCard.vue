<template>
  <!-- {{ facilities }} -->
  <v-card @click="$emit('wasClicked')">
    <v-img
      src="https://cdn.vuetifyjs.com/images/cards/cooking.png"
      class="white--text align-end"
      gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
      height="200px"
      width="130px"
      style="border-radius: 12px"
    >
      <v-card-title>{{ facilities.name }}</v-card-title>
      <v-card-subtitle>08.00 - 22.00</v-card-subtitle>
    </v-img>
  </v-card>
</template>

<script>
export default {
  name: "FacilityCard",
  props: {
    facilities: Object,
  },
};
</script>
