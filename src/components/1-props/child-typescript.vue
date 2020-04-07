<script lang="ts">
import { defineComponent, PropType } from '@vue/composition-api'

type Person = {
  id: number;
  name: string;
}

export default defineComponent({
  props: {
    names: {
      type: Array as () => string[],
      default: () => ['Alice', 'Bob']
    },
    staff: {
      type: Object as PropType<Person>,
      default: (): Person => ({ id: 1, name: '' })
    }
  },
  setup (props) {
    type Names = typeof props['names'] // -> string[]
    type Staff = typeof props['staff'] // -> Person
  }
})

</script>
