<template>
  <div>
    <v-bottom-navigation app :value="value" color="primary">
      <v-btn text to="/">
        <span>Beranda</span>

        <v-icon>mdi-history</v-icon>
      </v-btn>

      <v-btn text to="/voiceHelp">
        <span>Bantuan suara</span>

        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn text to="/railway">
        <span>Jalur Kereta</span>

        <v-icon>mdi-map-marker</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </div>
</template>

<script>
export default {
  data: () => ({ value: 0 }),
};
</script>
