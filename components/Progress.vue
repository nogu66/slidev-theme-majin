<script setup lang="ts">
interface ProgressItem {
  label: string
  percent: number
}

const props = defineProps<{
  items: ProgressItem[]
}>()
</script>

<template>
  <div class="progress-component">
    <div
      v-for="(item, index) in items"
      :key="index"
      class="progress-item"
    >
      <div class="progress-label">{{ item.label }}</div>
      <div class="progress-bar-container">
        <div class="progress-bar-bg">
          <div
            class="progress-bar-fill"
            :style="{ width: `${item.percent}%` }"
          ></div>
        </div>
        <div class="progress-percent">{{ item.percent }}%</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.progress-component {
  @apply flex flex-col gap-4;
}

.progress-item {
  @apply flex items-center;
}

.progress-label {
  @apply text-sm font-medium w-40 flex-shrink-0;
  color: var(--majin-text-primary, #333333);
}

.progress-bar-container {
  @apply flex-1 flex items-center gap-3;
}

.progress-bar-bg {
  @apply flex-1 h-4 rounded-full overflow-hidden;
  background: var(--majin-faint-gray, #e8eaed);
}

.progress-bar-fill {
  @apply h-full rounded-full transition-all duration-500;
  background: var(--majin-primary, #4285F4);
}

.progress-percent {
  @apply text-sm w-12 text-right;
  color: var(--majin-neutral-gray, #9e9e9e);
}
</style>
