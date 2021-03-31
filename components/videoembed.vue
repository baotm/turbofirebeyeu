<template>
  <b-overlay :show='videoLoading'>

    <b-embed
      aspect="16by9"
      allowfullscreen
      :src="srcVideo"
    ></b-embed>
  </b-overlay>
</template>

<script>
export default {
  props: ['srcVideo'],
  data () {
    return {
      videoLoading: true,
    }
  },
  mounted () {
    this.videoLoading = true;
  },
  updated: function () {

    this.videoLoading = false;

  },
}
</script>

<style>
</style>