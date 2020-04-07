<template>
  <div class="child">
    <h2 class="child-title">Child <small>（props を分割代入）</small></h2>
    count: {{ count }}<br />
    doubleCount: {{ doubleCount }}<br />
  </div>
</template>

<script lang="ts">
import { defineComponent, computed } from '@vue/composition-api'

export default defineComponent({
  props: {
    count: {
      type: Number,
      required: true
    }
  },
  setup ({ count }) {
    const doubleCount = computed(() => count * 2)

    return { doubleCount }
  }
})
</script>
