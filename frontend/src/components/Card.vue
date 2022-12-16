<template>
  <div class="card max-w-sm rounded overflow-hidden shadow-md bg-white">
    <div class="px-6 pt-4 pb-2">
      <div class="font-semibold text-md mb-2">
        {{ taskName }}
      </div>
    </div>

    <div class="px-6 pb-2">
      <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold mr-2 mb-2" :class="{'bg-red-400': weight === 1, 'bg-orange-400': weight > 0.5 && weight < 1, 'bg-yellow-400': weight === 0.5, 'bg-green-400': weight < 0.5}">
        Importance: {{ weight }}
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'CardComponent',
  props: {
    taskName: {
      type: String,
      required: true
    },
    weight: {
      type: Number,
      required: true
    }
  }
});
</script>

<style lang="scss" scoped>
.card {
  max-width: 288px;
}
</style>