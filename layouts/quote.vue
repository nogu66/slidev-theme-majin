<script setup lang="ts">
const props = defineProps<{
  text: string
  author: string
  subhead?: string
}>()
</script>

<template>
  <div class="slidev-layout quote-layout">
    <div class="quote-header">
      <h1 class="quote-title">
        <slot name="title" />
      </h1>
      <div class="title-underline"></div>
      <p v-if="props.subhead" class="quote-subhead">
        {{ props.subhead }}
      </p>
    </div>

    <div class="quote-content">
      <div class="quote-mark">"</div>
      <div class="quote-text">
        {{ props.text }}
      </div>
      <div class="quote-author">
        — {{ props.author }}
      </div>
    </div>
  </div>
</template>

<style scoped>
.quote-layout {
  @apply w-full h-full;
  background: white;
  padding: 3rem 2rem 2.5rem 2rem;
  display: flex;
  flex-direction: column;
}

.quote-header {
  @apply mb-6;
}

.quote-title {
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

.quote-subhead {
  @apply text-lg mt-2;
  color: var(--majin-text-secondary, #666666);
  line-height: 1.5;
}

.quote-content {
  @apply flex-1 flex flex-col items-center justify-center relative px-20;
}

.quote-mark {
  @apply absolute font-bold;
  font-size: 120px;
  line-height: 1;
  color: var(--majin-ghost-gray, #efefed);
  opacity: 0.5;
  left: 40px;
  top: 30%;
}

.quote-text {
  @apply text-2xl text-center mb-8 relative z-10;
  color: var(--majin-text-primary, #333333);
  line-height: 1.6;
  max-width: 700px;
}

.quote-author {
  @apply text-lg text-right relative z-10;
  color: var(--majin-neutral-gray, #9e9e9e);
  align-self: flex-end;
}
</style>
