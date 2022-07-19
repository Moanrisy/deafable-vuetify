<template>
  <div class="login">
    <div class="text-h4">Selamat Datang!</div>
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

          <v-col cols="12">
            <v-text-field
              v-model="password"
              :rules="nameRules"
              :counter="12"
              label="Kata Sandi"
              required
            ></v-text-field>
          </v-col>
          <v-btn color="success" class="mr-4" @click="submit"> Masuk </v-btn>

          <v-btn color="warning" class="mr-4" to="/forgetPassword">
            Lupa Password?
          </v-btn>
        </v-row>
      </v-container>
    </v-form>

    <div>Belum memiliki akun?</div>
    <v-btn class="mr-4" to="/signup"> Daftar Sekarang </v-btn>
  </div>
</template>

<script>
import Router from "../router";

export default {
  name: "Login",
  data: () => ({
    phoneNumber: "081234567890",
    fullName: "joko anwar",
    password: "test12",
    nameRules: [
      (v) => !!v || "Name is required",
      (v) => v.length <= 12 || "Name must be less than 10 characters",
    ],
  }),
  methods: {
    submit() {
      console.log(this.fullName);
      console.log(Router.push({ name: "home" }));
    },
  },
};
</script>
