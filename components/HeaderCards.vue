<script setup lang="ts">
interface CardItem {
  title: string
  desc?: string
}

const props = defineProps<{
  items: CardItem[]
  columns?: number
}>()

const cols = props.columns || 3
</script>

<template>
  <div
    class="header-cards-component"
    :style="{ 'grid-template-columns': `repeat(${cols}, 1fr)` }"
  >
    <div
      v-for="(item, index) in items"
      :key="index"
      class="header-card-item"
    >
      <div class="header-card-header">{{ item.title }}</div>
      <div v-if="item.desc" class="header-card-body">{{ item.desc }}</div>
    </div>
  </div>
</template>

<style scoped>
.header-cards-component {
  @apply grid gap-4;
}

.header-card-item {
  @apply rounded-lg border overflow-hidden;
  background: var(--majin-card-bg, #ffffff);
  border-color: var(--majin-card-border, #dadce0);
  transition: all 0.2s;
}

.header-card-item:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.header-card-header {
  @apply text-base font-bold px-5 py-3;
  background: var(--majin-primary, #4285F4);
  color: white;
}

.header-card-body {
  @apply text-sm p-5;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}
</style>
