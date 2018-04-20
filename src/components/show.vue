<template>
  <div @click.stop.prevent="click($event)" class="show">show</div>
</template>

<script>
import Bus from './bus.js'

export default {
  name: 'show.vue',
  components: {Bus},
  created () {
    Bus.$on('getTarget', target => {
      alert(target.className)
    })
    Bus.$off('getTarget', target => {
      alert(target.className)
    })
  },
  methods: {
    click (event) {
      Bus.$emit('get', event.target)
    }
  }
}
</script>

<style scoped>

</style>
