<template>
  <div class="parent">
    <h1 class="parent-title">Parent</h1>
    foo: {{ foo }}<br />
    bar: {{ bar }}<br />
    baz: {{ baz.toDateString() }}<br />
    <p class="caption">オブジェクトや配列を渡すと子コンポーネントで直接中身を変更できてしまう</p>
    <Child :obj="foo" :arr="bar" :dt="baz" />
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'
import Child from './child.vue'

export default {
  components: { Child },
  setup () {
    const foo = ref({
      num: 0
    })

    const bar = ref([])

    const baz = ref(new Date())

    return { foo, bar, baz }
  }
}
</script>
