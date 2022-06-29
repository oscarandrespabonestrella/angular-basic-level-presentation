<script setup lang="ts">
import { handleBackground } from '@slidev/theme-seriph/layoutHelper'
import { computed } from 'vue'


const props = defineProps({
  image: {
    type: String,
  },
  class: {
    type: String,
  },
})

const style = computed(() => handleBackground(props.image))
</script>

<template>
  <div class="grid grid-cols-3 w-full h-full">
    <div class="slidev-layout col-span-2 default" :class="props.class">
      <slot />
    </div>
    <div class="w-full w-full" :style="style" />
  </div>
</template>
