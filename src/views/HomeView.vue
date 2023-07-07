<template>
  <c-sidebar v-model:size="size" />

  <main class="m-auto">
    <table class="border-collapse">
      <tbody>
        <tr v-for="n in size.h" :key="n">
          <td v-for="j in size.w" :key="j" class="cursor-pointer hover:bg-slate-600 bg-slate-800" />
        </tr>
      </tbody>
    </table>
  </main>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import CSidebar from './CSidebar.vue';

const size = ref({ w: 10, h: 15 });
</script>

<style lang="scss" scoped>
table {
  td {
    $size: 30px;
    width: $size;
    height: $size;
  }
}

table,
th,
td {
  border: 2px solid #ffffff80;
}
</style>
