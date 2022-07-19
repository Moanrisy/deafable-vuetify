<template>
  <div class="forget-pass">
    <div class="text-h4">Lupa Password?</div>
    <div class="text-subtitle-1">
      Kita akan mengirimkan kode verifikasi ke nomor telfon kamu untuk mengatur
      ulang kata sandi mu
    </div>

    <v-form>
      <v-container>
        <v-row>
          <v-col cols="12">
            <v-text-field
              v-model="phoneNumber"
              :rules="nameRules"
              :counter="12"
              label="Nomor Telfon"
              required
            ></v-text-field>
          </v-col>

          <v-btn color="outlined" class="mr-4" @click="submit"> Kirim </v-btn>
        </v-row>
      </v-container>
    </v-form>

    <v-container>
      <v-row>
        <v-col align="center">1</v-col>
        <v-col align="center">2</v-col>
        <v-col align="center">3</v-col>
      </v-row>
      <v-row>
        <v-col align="center">4</v-col>
        <v-col align="center">5</v-col>
        <v-col align="center">6</v-col>
      </v-row>
      <v-row>
        <v-col align="center">7</v-col>
        <v-col align="center">8</v-col>
        <v-col align="center">9</v-col>
      </v-row>
      <v-row>
        <v-col></v-col>
        <v-col align="center">0</v-col>
        <v-col align="center">Delete</v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import Router from "../router";

export default {
  data: () => ({
    phoneNumber: "081234567890",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 12 || "Name must be less than 10 characters",
    ],
  }),
  methods: {
    submit() {
      console.log(this.phoneNumber);
      console.log(Router.push({ name: "home" }));
    },
  },
};
</script>
