<template>
  <xgplayer :options="playerOptions"></xgplayer>
</template>

<script>
export default {
  data () {
    return {
      playerOptions: {
        url: this.url,
        width: '100%' // Depends on its wrapper element.
      }
    }
  }
}
</script>