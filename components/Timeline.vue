<script setup lang="ts">
interface Milestone {
  date: string
  label: string
  state?: 'done' | 'next' | 'todo'
}

const props = defineProps<{
  milestones: Milestone[]
}>()

const getStateColor = (state?: string) => {
  if (state === 'done') return 'var(--majin-primary, #4285F4)'
  if (state === 'next') return 'var(--majin-accent, #f46524)'
  return 'var(--majin-neutral-gray, #9e9e9e)'
}
</script>

<template>
  <div class="timeline-component">
    <div class="timeline-line"></div>
    <div class="timeline-items">
      <div
        v-for="(milestone, index) in milestones"
        :key="index"
        class="timeline-item"
      >
        <div
          class="timeline-dot"
          :style="{ background: getStateColor(milestone.state) }"
        ></div>
        <div class="timeline-label">{{ milestone.label }}</div>
        <div class="timeline-date">{{ milestone.date }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.timeline-component {
  @apply relative w-full py-8;
}

.timeline-line {
  @apply absolute top-1/2 left-0 right-0 h-0.5;
  background: var(--majin-neutral-gray, #9e9e9e);
  opacity: 0.3;
  transform: translateY(-50%);
}

.timeline-items {
  @apply relative flex justify-between items-center;
}

.timeline-item {
  @apply flex flex-col items-center flex-1;
  position: relative;
}

.timeline-dot {
  @apply w-4 h-4 rounded-full mb-4 relative z-10;
  box-shadow: 0 0 0 4px white;
}

.timeline-label {
  @apply text-sm font-bold text-center mb-2;
  color: var(--majin-text-primary, #333333);
}

.timeline-date {
  @apply text-xs text-center;
  color: var(--majin-text-secondary, #666666);
}
</style>
