<template>
  <div id="app">
    <youtube
      :video-id="videoId"
      :player-vars="playerVars"
      @playing="playing"
      ref="youtube"
      disablepictureinpicture
      controlslist="nodownload"
      fitParent
      muted
      @ready="onReady"
      @cued="cued"
      @paused="paused"
    />
  </div>
</template>

<script>
export default {
  name: "app",
  computed: {
    player() {
      return this.$refs.youtube.player;
    },
  },
  data() {
    return {
      videoId: "rstRFJfBkWo",
      playerVars: {
        autoplay: 0,
      },
    };
  },
  methods: {
    playing() {
      console.log("o/ we are watching!!!");
    },
    onReady() {
      console.log("o/ I am ready!!!");
    },
    cued() {
      console.log("o/ we are cued!!!");
    },
    paused() {
      console.log("o/ I am paused!!!");
    },
  },
};
</script>
