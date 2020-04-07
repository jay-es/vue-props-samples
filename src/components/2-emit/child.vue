<template>
  <div class="child">
    <h2 class="child-title">Child</h2>
    <button @click="handleClick">Click me!</button>
  </div>
</template>

<script>
export default {
  setup (props, { emit }) {
    const handleClick = () => {
      emit('my-event', 123, 'abc', false)
    }

    return { handleClick }
  }
}
</script>
