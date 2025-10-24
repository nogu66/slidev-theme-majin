<script setup lang="ts">
const props = defineProps<{
  headers: string[]
  rows: string[][]
}>()
</script>

<template>
  <div class="table-component">
    <table class="data-table">
      <thead>
        <tr>
          <th v-for="(header, index) in headers" :key="index">
            {{ header }}
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(row, rowIndex) in rows" :key="rowIndex">
          <td v-for="(cell, cellIndex) in row" :key="cellIndex">
            {{ cell }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
.table-component {
  @apply w-full overflow-auto;
}

.data-table {
  @apply w-full border-collapse;
}

.data-table thead tr {
  background: var(--majin-table-header-bg, #f8f9fa);
}

.data-table th {
  @apply px-4 py-3 text-left text-sm font-bold;
  color: var(--majin-text-primary, #333333);
  border: 1px solid var(--majin-card-border, #dadce0);
}

.data-table td {
  @apply px-4 py-3 text-sm;
  color: var(--majin-text-primary, #333333);
  border: 1px solid var(--majin-card-border, #dadce0);
}

.data-table tbody tr:hover {
  background: var(--majin-background-gray, #f8f9fa);
}
</style>
