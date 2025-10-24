<script setup lang="ts">
const props = defineProps<{
  subhead?: string
}>()
</script>

<template>
  <div class="slidev-layout process-layout">
    <div class="process-header">
      <h1 class="process-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="process-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="process-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.process-layout {
  @apply w-full h-full;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.process-header {
  @apply mb-6;
}

.process-title {
  @apply text-3xl font-bold mb-2;
  color: var(--majin-text-primary, #333333);
  line-height: 1.3;
}

.title-underline {
  width: 260px;
  height: 4px;
  background: var(--majin-primary, #4285F4);
  margin: 0.5rem 0 1rem 0;
}

.process-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.process-content {
  @apply flex-1 overflow-auto;
}

.process-content :deep(ol) {
  @apply space-y-4;
  counter-reset: process-counter;
  list-style: none;
  padding-left: 0;
}

.process-content :deep(li) {
  @apply relative pl-16 pb-6;
  counter-increment: process-counter;
}

.process-content :deep(li::before) {
  content: counter(process-counter);
  @apply absolute left-0 top-0 w-12 h-12 rounded-full flex items-center justify-center text-xl font-bold;
  background: var(--majin-primary, #4285F4);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
}

.process-content :deep(li::after) {
  content: '';
  @apply absolute left-6 top-12 w-0.5 h-full;
  background: var(--majin-card-border, #dadce0);
}

.process-content :deep(li:last-child::after) {
  display: none;
}

.process-content :deep(strong) {
  @apply font-bold block mb-2;
  color: var(--majin-text-primary, #333333);
  font-size: 1.1rem;
}

.process-content :deep(li) {
  @apply text-base leading-relaxed;
  color: var(--majin-text-secondary, #666666);
}
</style>
