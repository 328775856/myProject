<template>
  <div id="app">
    <!--<img src="./assets/logo.png">-->
    <!--<br>-->
    <!--<router-link to="/">home</router-link>-->
    <!--<router-link transition="" to="main">main</router-link>-->
    <!--<router-link to="/HelloWorld">HelloWorld</router-link>-->
    <router-view/>
    <button @click="show = !show">Toggle</button>
    <transition @enter="enter" @leave="leave">
      <p v-if="show">hello</p>
    </transition>
  </div>
</template>

<script>/* eslint-disable */
  export default {
    name: 'App',
    data() {
      return {
        show: true
      }
    },
    methods:{
      enter(el,done){
        el.style.opacity = 0
      },
      leave(el,done){
        el.style.opacity = 0
      }
    }
  }
</script>

<style>
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  /*.fade-enter-active, .fade-leave-active {*/
    /*transition: all .5s;*/
  /*}*/
  /*.fade-enter, .fade-leave-to !* .fade-leave-active below version 2.1.8 *! {*/
    /*transform: translateY(100%);*/
  /*}*/
</style>
