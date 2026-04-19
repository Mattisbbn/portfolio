<script setup>
defineProps({
  name: String,
});
</script>

<template>
  <button
    class="px-4 py-2 backdrop-blur-xs cursor-pointer border-2 rounded-xl flex items-center justify-center font-bold text-xl gap-4">
    {{ name }}
    <slot name="icon" />
  </button>
</template>
