<script setup lang="ts">
const props = defineProps<{
  sectionNo?: number
}>()
</script>

<template>
  <div class="slidev-layout section-layout">
    <div class="section-background">
      <div v-if="props.sectionNo" class="ghost-number">
        {{ props.sectionNo }}
      </div>
    </div>
    <div class="section-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.section-layout {
  @apply w-full h-full relative flex items-center justify-start;
  background: white;
  padding: 3rem 4rem;
}

.section-background {
  @apply absolute inset-0 overflow-hidden;
  pointer-events: none;
}

.ghost-number {
  @apply absolute font-bold;
  font-size: 24rem;
  line-height: 1;
  color: var(--majin-ghost-gray, #efefed);
  opacity: 0.3;
  left: 2rem;
  top: 50%;
  transform: translateY(-50%);
  user-select: none;
}

.section-content {
  @apply relative z-10 max-w-4xl;
  margin-left: 2rem;
}

.section-content :deep(h1) {
  @apply text-5xl font-bold mb-4;
  color: var(--majin-text-primary, #333333);
  line-height: 1.2;
}

.section-content :deep(p) {
  @apply text-lg mt-4;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}
</style>
