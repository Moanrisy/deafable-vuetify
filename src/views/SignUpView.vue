<template>
  <div class="signUp">
    <div class="text-h4">Gabung Sekarang!</div>
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
              v-model="fullName"
              :rules="nameRules"
              :counter="10"
              label="Nama Pengguna"
              required
            ></v-text-field>
          </v-col>

          <v-col cols="12">
            <v-text-field
              v-model="password"
              :rules="nameRules"
              :counter="10"
              label="Kata Sandi"
              required
            ></v-text-field>
          </v-col>

          <v-btn color="success" class="mr-4" @click="submit"> Daftar </v-btn>
        </v-row>
      </v-container>
    </v-form>

    <div>Sudah memiliki akun?</div>
    <v-btn class="mr-4" to="/login"> Masuk </v-btn>
  </div>
</template>

<script>
export default {
  name: "Signup",
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
    },
  },
};
</script>
