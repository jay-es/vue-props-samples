<template>
  <div class="parent">
    <h1 class="parent-title">Parent</h1>
    num: {{ num }}<br />
    <p class="caption">子コンポーネントのイベントの引数で親の変数 num を更新する</p>
    <p class="caption">親での受け取り方が違うだけで、子コンポーネントは全部同じ</p>
    <Child :count.sync="num" />
    <Child :count="num" @update:count="num = $event" />
  </div>
</template>

<script>
import { ref } from '@vue/composition-api'
import Child from './child.vue'

export default {
  components: { Child },
  setup () {
    const num = ref(0)

    const handleEvent = (newVal) => {
      num.value = newVal
    }

    return { num, handleEvent }
  }
}
</script>
