<template>
  <div class="hello">
    <h2>{{msg}}</h2>
    <hr>
    <h3>{{$store.state.count}}</h3>
    <button @click="add(10)">+</button>
    <button @click="reduce">-</button>
    <div :value="count">{{count}}</div>
    <p>
      <button @click="addAction">+</button>
      <button @click="reduceAction">-</button>
    </p>
  </div>
</template>

<script>
import store from '../../store'
import {mapState, mapMutations, mapGetters, mapActions} from 'vuex'
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Hello Vuex',
      value: ''
    }
  },
  computed: {
    ...mapState(['count']),
    ...mapGetters(['count'])
  },
  methods: {
    ...mapMutations([
      'add', 'reduce'
    ]),
    ...mapActions(['addAction', 'reduceAction'])
  },
  store
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
