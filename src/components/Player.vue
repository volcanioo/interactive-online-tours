<template>
  <div class="player">
    <video
      muted
      ref="playerInstance"
      @timeupdate="onTimeUpdateListener"
    >
      <source :src="src" type="video/mp4">
    </video>
    <button
      @click="start"
      class="player__play"
    >
      play/pause
    </button>
    <div class="player__time">
      <span :style="`width: ${currentPercantage}%`"></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Player',
  props: {
    src: String,
  },
  data() {
    return {
      currentPercantage: 0,
    };
  },
  methods: {
    onTimeUpdateListener(e) {
      this.currentPercantage = (e.target.currentTime / e.target.duration) * 100;
    },
    start() {
      if (this.$refs.playerInstance.paused) {
        this.$refs.playerInstance.play();
      } else {
        this.$refs.playerInstance.pause();
      }
    },
  },
};
</script>
<style lang="scss" scoped>
.player {
  background: black;
  width: 100%;
  height: calc(100vh - 80px);
  position: relative;
  video {
    width: 100%;
    height: calc(100vh - 80px - 2px);
  }
  &__play,
  &__time {
    position: absolute;
    bottom: 40px;
    height: 60px;
    left: 30px;
  }
  &__time {
    width: 100%;
    background: red;
    left: 0;
    height: 10px;
    bottom: 0;
    span {
      display: block;
      background: white;
      height: 100%;
      width: 0%;
      transition: all .5s cubic-bezier(0.075, 0.82, 0.165, 1);
    }
  }
}
</style>
