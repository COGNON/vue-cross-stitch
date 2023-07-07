<template>
  <span class="form-control">
    <label class="label">{{ label }}</label>
    <input v-model="modelValue" type="number" class="input input-bordered input-accent" />
  </span>
</template>

<script setup lang="ts">
defineProps<{ label: string }>();
const modelValue = defineModel({ default: 10 });
</script>
