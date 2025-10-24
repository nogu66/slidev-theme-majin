<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  date?: string
}>()
</script>

<template>
  <div class="slidev-layout title-layout">
    <div class="title-container">
      <div class="title-content">
        <slot />
      </div>
      <div v-if="props.date" class="title-date">
        {{ props.date }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.title-layout {
  @apply w-full h-full flex items-center justify-center;
  background: white;
  padding: 3rem;
}

.title-container {
  @apply w-full max-w-4xl;
}

.title-content {
  @apply mb-16;
}

.title-content :deep(h1) {
  @apply text-5xl font-bold mb-4;
  color: var(--majin-text-primary, #333333);
  line-height: 1.2;
}

.title-content :deep(p) {
  @apply text-xl mt-4;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}

.title-date {
  @apply text-base;
  color: var(--majin-text-secondary, #666666);
  margin-top: 2rem;
}
</style>
