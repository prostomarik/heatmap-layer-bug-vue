<template>
  <div id="app">
    <DeckMap/>
  </div>
</template>

<script>
import DeckMap from '@/DeckMap.vue'

export default {
  name: 'App',
  components: { DeckMap }
}
</script>

<style>
#app {
  width: 100vw;
  overflow: hidden;
}
</style>