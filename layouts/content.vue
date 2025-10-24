<script setup lang="ts">
import { useSlots } from 'vue'

const props = defineProps<{
  twoColumn?: boolean
  subhead?: string
}>()

const slots = useSlots()
</script>

<template>
  <div class="slidev-layout content-layout">
    <div class="content-header">
      <h1 class="content-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="content-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="content-body" :class="{ 'two-column': props.twoColumn }">
      <slot />
    </div>

    <div class="content-footer">
      <div class="page-number">
        <slot name="page" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.content-layout {
  @apply w-full h-full relative;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.content-header {
  @apply mb-6;
}

.content-title {
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

.content-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.content-body {
  @apply flex-1 overflow-auto;
}

.content-body.two-column {
  @apply grid grid-cols-2 gap-8;
}

.content-body :deep(ul),
.content-body :deep(ol) {
  @apply space-y-2 pl-6;
}

.content-body :deep(li) {
  @apply text-base leading-relaxed;
  color: var(--majin-text-primary, #333333);
}

.content-body :deep(strong) {
  @apply font-bold;
  color: var(--majin-primary, #4285F4);
}

.content-body :deep(p) {
  @apply text-base leading-relaxed mb-3;
  color: var(--majin-text-primary, #333333);
}

.content-footer {
  @apply absolute bottom-4 right-4;
}

.page-number {
  @apply text-sm;
  color: var(--majin-text-secondary, #999999);
}
</style>
