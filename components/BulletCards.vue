<script setup lang="ts">
interface CardItem {
  title: string
  desc: string
}

const props = defineProps<{
  items: CardItem[]
}>()

// Maximum 3 items
const displayItems = props.items.slice(0, 3)
</script>

<template>
  <div class="bullet-cards-component">
    <div
      v-for="(item, index) in displayItems"
      :key="index"
      class="bullet-card-item"
    >
      <div class="bullet-number">{{ index + 1 }}</div>
      <div class="bullet-card-content">
        <div class="bullet-card-title">{{ item.title }}</div>
        <div class="bullet-card-desc">{{ item.desc }}</div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bullet-cards-component {
  @apply flex flex-col gap-4;
}

.bullet-card-item {
  @apply flex items-start p-6 rounded-lg;
  background: var(--majin-background-gray, #f8f9fa);
  border: 1px solid var(--majin-card-border, #dadce0);
}

.bullet-number {
  @apply flex items-center justify-center w-12 h-12 rounded-full mr-5 flex-shrink-0 text-2xl font-bold;
  background: var(--majin-primary, #4285F4);
  color: white;
}

.bullet-card-content {
  @apply flex-1;
}

.bullet-card-title {
  @apply text-lg font-bold mb-2;
  color: var(--majin-text-primary, #333333);
}

.bullet-card-desc {
  @apply text-sm;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}
</style>
