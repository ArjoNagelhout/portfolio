<template>
  <div id="app">
    <InformationCard/>
  </div>
</template>

<script>
import InformationCard from './components/InformationCard.vue'

export default {
  name: 'app',
  components: {
    InformationCard
  }
}
</script>

<style>
#app {
  border:1px solid black;
}
</style>
