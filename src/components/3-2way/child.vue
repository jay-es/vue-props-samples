<template>
  <div class="child">
    <h2 class="child-title">Child</h2>
    <button @click="handleClick">Click me!</button>
  </div>
</template>

<script>
export default {
  props: {
    count: Number
  },
  setup (props, { emit }) {
    // ボタンのイベントハンドラ
    const handleClick = () => {
      emit('my-event', props.count + 1)
    }

    return { handleClick }
  }
}
</script>
