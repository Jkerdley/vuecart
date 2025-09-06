<script setup>
import { computed } from 'vue'
const props = defineProps({
  total: {
    type: Number,
    required: true,
  },
})

const TAX = 0.1

const tax = computed(() => {
  return (props.total * TAX).toFixed(2)
})
</script>

<template>
  <tr>
    <td colspan="5">
      <div class="basket-table__summary">
        <p class="basket-table__total">
          Total <b>$ {{ total.toFixed(2) }}</b>
        </p>
        <p>Tax $ {{ tax }}</p>
      </div>
    </td>
  </tr>
</template>
<style scoped>
.basket-table__summary {
  text-align: right;
  padding: 2rem 5rem;
}

.basket-table__total {
  font-size: 1.4rem;
}
</style>
