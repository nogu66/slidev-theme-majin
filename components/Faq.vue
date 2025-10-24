<script setup lang="ts">
interface FaqItem {
  q: string
  a: string
}

const props = defineProps<{
  items: FaqItem[]
}>()
</script>

<template>
  <div class="faq-component">
    <div
      v-for="(item, index) in items"
      :key="index"
      class="faq-item"
    >
      <div class="faq-question">
        <span class="faq-q-label">Q.</span>
        {{ item.q }}
      </div>
      <div class="faq-answer">
        <span class="faq-a-label">A.</span>
        {{ item.a }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.faq-component {
  @apply flex flex-col gap-6;
}

.faq-item {
  @apply space-y-2;
}

.faq-question {
  @apply text-base font-bold flex gap-2;
  color: var(--majin-text-primary, #333333);
}

.faq-q-label {
  @apply flex-shrink-0 font-bold;
  color: var(--majin-primary, #4285F4);
}

.faq-answer {
  @apply text-sm pl-6 flex gap-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.6;
}

.faq-a-label {
  @apply flex-shrink-0 font-bold;
  color: var(--majin-text-secondary, #666666);
}
</style>
