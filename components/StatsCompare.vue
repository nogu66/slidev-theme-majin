<script setup lang="ts">
interface StatItem {
  label: string
  leftValue: string
  rightValue: string
  trend?: 'up' | 'down' | 'neutral'
}

const props = defineProps<{
  stats: StatItem[]
}>()

const getTrendIcon = (trend?: string) => {
  if (trend === 'up') return '↑'
  if (trend === 'down') return '↓'
  return '→'
}

const getTrendColor = (trend?: string) => {
  if (trend === 'up') return 'var(--majin-primary, #4285F4)'
  if (trend === 'down') return '#ea4335'
  return 'var(--majin-neutral-gray, #9e9e9e)'
}
</script>

<template>
  <div class="stats-compare-component">
    <div
      v-for="(stat, index) in stats"
      :key="index"
      class="stat-row"
    >
      <div class="stat-label">{{ stat.label }}</div>
      <div class="stat-values">
        <div class="stat-value left-value">{{ stat.leftValue }}</div>
        <div
          class="stat-trend"
          :style="{ color: getTrendColor(stat.trend) }"
        >
          {{ getTrendIcon(stat.trend) }}
        </div>
        <div class="stat-value right-value">{{ stat.rightValue }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.stats-compare-component {
  @apply flex flex-col gap-3;
}

.stat-row {
  @apply flex items-center p-4 rounded-lg;
  background: var(--majin-background-gray, #f8f9fa);
}

.stat-label {
  @apply text-sm font-medium w-48 flex-shrink-0;
  color: var(--majin-text-primary, #333333);
}

.stat-values {
  @apply flex-1 flex items-center justify-between gap-4;
}

.stat-value {
  @apply text-lg font-bold flex-1 text-center;
  color: var(--majin-text-primary, #333333);
}

.stat-trend {
  @apply text-2xl font-bold;
}
</style>
