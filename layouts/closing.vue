<script setup lang="ts">
</script>

<template>
  <div class="slidev-layout closing-layout">
    <div class="closing-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.closing-layout {
  @apply w-full h-full flex items-center justify-center;
  background: white;
  padding: 3rem;
}

.closing-content {
  @apply text-center max-w-4xl;
}

.closing-content :deep(h1) {
  @apply text-5xl font-bold mb-6;
  color: var(--majin-text-primary, #333333);
  line-height: 1.2;
}

.closing-content :deep(p) {
  @apply text-xl mt-6;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}

.closing-content :deep(a) {
  @apply text-lg;
  color: var(--majin-primary, #4285F4);
  text-decoration: none;
}

.closing-content :deep(a:hover) {
  text-decoration: underline;
}
</style>
