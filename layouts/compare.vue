<script setup lang="ts">
import { useSlots } from 'vue'

const props = defineProps<{
  leftTitle: string
  rightTitle: string
  subhead?: string
}>()

const slots = useSlots()
</script>

<template>
  <div class="slidev-layout compare-layout">
    <div class="compare-header">
      <h1 class="compare-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="compare-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="compare-content">
      <div class="compare-box left-box">
        <div class="box-header">
          {{ props.leftTitle }}
        </div>
        <div class="box-body">
          <slot name="left" />
        </div>
      </div>

      <div class="compare-box right-box">
        <div class="box-header">
          {{ props.rightTitle }}
        </div>
        <div class="box-body">
          <slot name="right" />
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.compare-layout {
  @apply w-full h-full;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.compare-header {
  @apply mb-6;
}

.compare-title {
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

.compare-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.compare-content {
  @apply flex-1 grid grid-cols-2 gap-6;
}

.compare-box {
  @apply border rounded-lg overflow-hidden;
  background: var(--majin-background-white, #ffffff);
  border-color: var(--majin-card-border, #dadce0);
  display: flex;
  flex-direction: column;
}

.box-header {
  @apply text-xl font-bold px-6 py-4;
  background: var(--majin-primary, #4285F4);
  color: white;
  text-align: center;
}

.box-body {
  @apply flex-1 p-6 overflow-auto;
}

.box-body :deep(ul),
.box-body :deep(ol) {
  @apply space-y-2 pl-6;
}

.box-body :deep(li) {
  @apply text-base leading-relaxed;
  color: var(--majin-text-primary, #333333);
}

.box-body :deep(strong) {
  @apply font-bold;
}

.box-body :deep(p) {
  @apply text-base leading-relaxed mb-3;
  color: var(--majin-text-primary, #333333);
}
</style>
