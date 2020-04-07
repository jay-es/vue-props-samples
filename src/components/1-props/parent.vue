<template>
  <div class="parent">
    <h1 class="parent-title">Parent</h1>
    foo: <input type="text" v-model="foo" /><br />
    bar: <input type="number" v-model.number="bar" /><br />
    <p class="caption">bar を書き換えても、下側の子コンポーネントの doubleCount は不変</p>

    <Child :title="foo" :count="bar" />
    <Child2 :title="foo" :count="bar" />
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'
import Child from './child.vue'
import Child2 from './child-destructure.vue'

export default {
  components: { Child, Child2 },
  setup () {
    const foo = ref('abc')
    const bar = ref(123)

    return { foo, bar }
  }
}
</script>

<style scoped>
  input {
    width: 4em;
  }
</style>
