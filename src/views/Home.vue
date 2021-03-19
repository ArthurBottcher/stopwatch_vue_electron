<template>
  <v-card dark tile width="400px" height="150px">
    <v-card-title class="justify-center mt-2" label style="font-size: 50px">
      {{ watch }}
    </v-card-title>
    <v-card-actions class="justify-space-around pa-4">
      <v-btn
        color="success"
        class="mx-2"
        width="100px"
        outlined
        @click="timeStart"
      >
        Start</v-btn
      >

      <v-btn
        color="error"
        class="mx-2"
        width="100px"
        outlined
        @click="timePaused"
      >
        Pause
      </v-btn>

      <v-btn
        color="warning"
        class="mx-2"
        width="100px"
        outlined
        @click="timeReset"
        >Reset</v-btn
      >
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",
  components: {},
  data: () => {
    return {
      watch: "00:00:00:00",
      millisecound: 0,
      timer: 0,
      color: "",
    };
  },
  methods: {
    timeStart() {
      this.color = "info";
      clearInterval(this.timer);
      this.timer = window.setInterval(() => {
        this.millisecound += 10;
        let dateTimer = new Date(this.millisecound);

        this.watch =
          ("0" + dateTimer.getUTCHours()).slice(-2) +
          ":" +
          ("0" + dateTimer.getUTCMinutes()).slice(-2) +
          ":" +
          ("0" + dateTimer.getUTCSeconds()).slice(-2) +
          ":" +
          ("0" + dateTimer.getUTCMilliseconds()).slice(-3, -1);
      }, 10);
    },

    timePaused() {
      this.color = "error";
      clearInterval(this.timer);
    },

    timeReset(): void {
      this.timer;
      this.millisecound = 0;
      this.watch = "00:00:00:00";
    },
  },
});
</script>
<style lang="scss"></style>
