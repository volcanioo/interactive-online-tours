<template>
  <div>
    <Header></Header>
    <div class="wrapper">
      <div class="player-area">
        <Player :src="require('@/assets/videos/tour.mp4')"></Player>
      </div>
      <div class="content-area">
        s
      </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/Header.vue';
import Player from '@/components/Player.vue';

export default {
  name: 'Home',
  components: {
    Header,
    Player,
  },
};
</script>
<style lang="scss">
.wrapper {
  display: flex;
  flex-direction: row;
  .player-area {
    width: 80%;
  }
}
</style>
