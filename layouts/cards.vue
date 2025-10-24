<script setup lang="ts">
const props = defineProps<{
  columns?: number
  subhead?: string
}>()
</script>

<template>
  <div class="slidev-layout cards-layout">
    <div class="cards-header">
      <h1 class="cards-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="cards-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="cards-content">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.cards-layout {
  @apply w-full h-full;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.cards-header {
  @apply mb-6;
}

.cards-title {
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

.cards-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.cards-content {
  @apply flex-1 overflow-auto;
}
</style>
