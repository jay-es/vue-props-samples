<template>
  <div id="app">
    <h1>1. props</h1>
    <Parent1 />
    <h1>2. emit</h1>
    <Parent2 />
    <h1>3. 双方向バインディング</h1>
    <Parent3 />
    <h1>3-1. v-model</h1>
    <Parent31 />
    <h1>3-2. .sync</h1>
    <Parent32 />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Parent1 from './components/1-props/parent.vue'
import Parent2 from './components/2-emit/parent.vue'
import Parent3 from './components/3-2way/parent.vue'
import Parent31 from './components/31-v-model/parent.vue'
import Parent32 from './components/32-sync/parent.vue'

export default Vue.extend({
  name: 'App',
  components: {
    Parent1,
    Parent2,
    Parent3,
    Parent31,
    Parent32
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.parent {
  margin: 1em;
  padding: 0 1em;
  border: 1px solid khaki;
  background-color: lightyellow;
}

.child {
  margin: 1em 0;
  padding: 0 1em 1em;
  border: 1px solid lightskyblue;
  background-color: aliceblue;
}

.parent-title,
.child-title {
  font-size: 1em;
}

.caption {
  margin: 0.3em;
  font-size: 0.7em;
}

</style>
