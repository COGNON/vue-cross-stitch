<template>
  <li class="flex flex-row items-center hover:bg-slate-700 hover:rounded-md py-0.5">
    <span :style="{ backgroundColor: color.RGB_COLOR }" class="w-5 h-5 mr-2 rounded-md" />
    <span>{{ color.DMC_COLOR }}</span>
  </li>
</template>

<script setup lang="ts">
defineProps<{ color: { DMC_COLOR: string; COLOR_NAME: string; RGB_COLOR: string } }>();
</script>
