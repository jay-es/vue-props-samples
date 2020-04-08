<template>
  <div class="child">
    <h2 class="child-title">Child</h2>
    <button @click="handleClick">Click me!</button>
  </div>
</template>

<script>
export default {
  props: {
    obj: Object,
    arr: Array,
    dt: Date
  },
  setup (props) {
    // ボタンのイベントハンドラ
    const handleClick = () => {
      props.obj.num += 1 // 親コンポーネントの foo.num に反映される
      props.arr.push(0) // 親コンポーネントの bar の要素が増加する
      props.arr[0] += 1 // 配列内の値を変更することもできる
      props.dt.setDate(Math.random()) // 日付が変わる
    }

    return { handleClick }
  }
}
</script>
