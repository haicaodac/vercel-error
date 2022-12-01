<template>
  <button @click="onShow">Show Hello World</button>
  <HelloWorld v-if="show" msg="Welcome to Your Vue.js App"/>
</template>

<script>
import { defineAsyncComponent } from 'vue';

const HelloWorld = defineAsyncComponent(() =>
  import('./components/HelloWorld.vue')
)

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return {
      show: false,
    }
  },
  methods: {
    onShow() {
      this.show = true
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
