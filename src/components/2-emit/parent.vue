<template>
  <div class="parent">
    <h1 class="parent-title">Parent</h1>
    <p class="caption">small>子コンポーネントでイベント発生したら、親が引数を alert</p>
    <Child @my-event="handleEvent" />
  </div>
</template>

<script>
import Child from './child.vue'

export default {
  components: { Child },
  setup () {
    const handleEvent = (...args) => {
      alert(args)
    }

    return { handleEvent }
  }
}
</script>
