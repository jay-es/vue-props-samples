<template>
  <div class="child">
    <h2 class="child-title">Child</h2>
    title: {{ title }}<br />
    count: {{ count }}<br />
    doubleCount: {{ doubleCount }}<br />
  </div>
</template>

<script>
import { computed } from '@vue/composition-api'

export default ({
  // props: ['title', 'count']

  // props: {
  //   title: String,
  //   count: Number
  // }

  props: {
    title: {
      type: String,
      required: true
    },
    count: {
      type: Number,
      default: 0
    }
  },
  setup (props) {
    const doubleCount = computed(() => props.count * 2)

    return { doubleCount }
  }
})
</script>
