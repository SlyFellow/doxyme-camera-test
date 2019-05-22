<template>
  <div class="video-wrap">
    <video ref="video" autoplay muted></video>
  </div>
</template>

<script>
  import DoxyMe from '@doxyme/media-access'

  export default {
    name: 'Video',
    mounted() {
      this.requestMediaAccess()
    },
    methods: {
      async requestMediaAccess() {
        try {
          this.$refs.video.srcObject = await DoxyMe.requestMediaAccess()
        } catch (e) {

        }
      },
    },
  }
</script>

<style scoped>
  .video-wrap {
    display: flex;
    justify-content: center;
    margin: 30px 0;
  }

  video {
    background-color: #ccc;
  }
</style>
