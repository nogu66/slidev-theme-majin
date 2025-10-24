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
    class="cards-component"
    :style="{ 'grid-template-columns': `repeat(${cols}, 1fr)` }"
  >
    <div
      v-for="(item, index) in items"
      :key="index"
      class="card-item"
    >
      <div class="card-title">{{ item.title }}</div>
      <div v-if="item.desc" class="card-desc">{{ item.desc }}</div>
    </div>
  </div>
</template>

<style scoped>
.cards-component {
  @apply grid gap-4;
}

.card-item {
  @apply p-6 rounded-lg border;
  background: var(--majin-card-bg, #ffffff);
  border-color: var(--majin-card-border, #dadce0);
  transition: all 0.2s;
}

.card-item:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}

.card-title {
  @apply text-lg font-bold mb-2;
  color: var(--majin-text-primary, #333333);
}

.card-desc {
  @apply text-sm;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}
</style>
