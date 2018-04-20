<template>
  <div class="main">main
    <click></click>
    <show></show>
  </div>

</template>

<script>
import Click from './click.vue'
import Show from './show.vue'

export default {
  name: 'main.vue',
  components: {Click, Show}
}
</script>

<style scoped>

</style>
