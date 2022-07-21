<template>
  <div class="voice-help">
    <v-toolbar flat>
      <!-- <v-app-bar-nav-icon></v-app-bar-nav-icon> -->
      <v-btn icon>
        <v-icon @click="goBack">mdi-arrow-left</v-icon>
      </v-btn>
      <v-toolbar-title>Bantuan Suara</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-help-circle-outline</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-message</v-icon>
      </v-btn>
    </v-toolbar>

    <v-container class="chat-container">
      <div
        class="message d-flex flex-column"
        v-for="(message, index) in messages"
        v-bind:key="index"
        :class="
          ({ own: message.user == 'username' },
          userName == message.user ? 'align-end' : '')
        "
      >
        <div
          class="username"
          v-if="index > 0 && messages[index - 1].user != message.user"
        >
          {{ message.user }}
        </div>
        <div class="username" v-if="index == 0">{{ message.user }}</div>
        <div style="margin-top: 5px"></div>
        <div class="content">
          <!-- <div v-html="message.content"></div> -->
          <v-chip>
            {{ message.content }}
          </v-chip>
          <chat-image
            v-if="message.image"
            :imgsrc="message.image"
            @imageLoad="imageLoad"
          ></chat-image>
        </div>
      </div>

      <v-text-field
        v-model="message"
        label="Ketik di sini"
        solo
        rounded
        append-outer-icon="mdi-microphone"
        @click:append-outer="openMic"
        @keydown.enter="sendMessage"
      ></v-text-field>
    </v-container>

    <BottomNavigation />
  </div>
</template>

<script>
import BottomNavigation from "../components/BottomNavigation.vue";
import Router from "../router";

export default {
  data: () => ({
    userName: "Joko",
    message: "",
    messages: [
      {
        user: "Joko",
        content: "Hi",
      },
      {
        user: "Bot",
        content: "Hello",
      },
    ],
  }),
  components: {
    BottomNavigation,
  },
  methods: {
    goBack() {
      console.log("going back");
      Router.push({ name: "home" });
    },
    sendMessage() {
      console.log(this.message);
      this.message = "";
    },
    openMic() {
      alert("mic clicked");
    },
  },
};
</script>

<style>
.chat-container {
  position: absolute;
  bottom: 0;
  margin-bottom: -32px;
}
</style>
