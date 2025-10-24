<script setup lang="ts">
const props = defineProps<{
  leftTitle: string
  rightTitle: string
  subhead?: string
}>()
</script>

<template>
  <div class="slidev-layout stats-compare-layout">
    <div class="stats-header">
      <h1 class="stats-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="stats-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="stats-content">
      <div class="stats-columns">
        <div class="column-header left-header">{{ props.leftTitle }}</div>
        <div class="column-header right-header">{{ props.rightTitle }}</div>
      </div>
      <div class="stats-body">
        <slot />
      </div>
    </div>
  </div>
</template>

<style scoped>
.stats-compare-layout {
  @apply w-full h-full;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.stats-header {
  @apply mb-6;
}

.stats-title {
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

.stats-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.stats-content {
  @apply flex-1 flex flex-col;
}

.stats-columns {
  @apply grid grid-cols-2 gap-6 mb-4;
}

.column-header {
  @apply text-xl font-bold py-3 px-4 text-center rounded-lg;
  background: var(--majin-background-gray, #f8f9fa);
  color: var(--majin-text-primary, #333333);
}

.stats-body {
  @apply flex-1 overflow-auto;
}
</style>
