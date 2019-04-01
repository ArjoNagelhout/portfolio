<template>
  <div id="app">
    <InformationCard/>
    <Timeline/>
  </div>
</template>

<script>
import InformationCard from './components/InformationCard.vue'
import Timeline from './components/Timeline.vue'

export default {
  name: 'app',
  components: {
    InformationCard,
    Timeline
  }
}
</script>

<style>
#app {
  border:1px solid black;
}
</style>
