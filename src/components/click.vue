<template>
  <div class="click" @click.stop.prevent="doClick($event)">click</div>
</template>

<script>
import Bus from './bus.js'

export default {
  name: 'click.vue',
  components: {Bus},
  data () {
    return {
      data: 'asda'
    }
  },
  created () {
    Bus.$on('get', target => {
      alert(target.className + this.data)
    })
    Bus.$off('get', target => {
      alert(target.className)
    })
  },
  methods: {
    doClick (event) {
      Bus.$emit('getTarget', event.target)
    }
  }
}
</script>

<style scoped>

</style>
