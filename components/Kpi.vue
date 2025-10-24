<script setup lang="ts">
interface KpiItem {
  label: string
  value: string
  change: string
  status: 'good' | 'bad' | 'neutral'
}

const props = defineProps<{
  items: KpiItem[]
  columns?: number
}>()

const cols = props.columns || 4

const getStatusColor = (status: string) => {
  if (status === 'good') return 'var(--majin-primary, #4285F4)'
  if (status === 'bad') return '#ea4335'
  return 'var(--majin-neutral-gray, #9e9e9e)'
}
</script>

<template>
  <div
    class="kpi-component"
    :style="{ 'grid-template-columns': `repeat(${cols}, 1fr)` }"
  >
    <div
      v-for="(item, index) in items"
      :key="index"
      class="kpi-card"
    >
      <div class="kpi-label">{{ item.label }}</div>
      <div class="kpi-value">{{ item.value }}</div>
      <div
        class="kpi-change"
        :style="{ color: getStatusColor(item.status) }"
      >
        {{ item.change }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.kpi-component {
  @apply grid gap-4;
}

.kpi-card {
  @apply p-6 rounded-lg border flex flex-col items-center justify-center text-center;
  background: var(--majin-card-bg, #ffffff);
  border-color: var(--majin-card-border, #dadce0);
  min-height: 180px;
}

.kpi-label {
  @apply text-sm mb-4;
  color: var(--majin-neutral-gray, #9e9e9e);
}

.kpi-value {
  @apply text-4xl font-bold mb-3;
  color: var(--majin-text-primary, #333333);
}

.kpi-change {
  @apply text-sm font-bold;
}
</style>
