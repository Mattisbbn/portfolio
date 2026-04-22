<script setup>
defineProps({
  name: String,
  active: Boolean
});
</script>

<template>
  <button
    class="px-4 py-2 backdrop-blur-xs text-bold  cursor-pointer border-2 rounded-xl flex items-center justify-center font-bold text-xl gap-4"
    :class="{ 'bg-primary text-white border-primary': active }">
    {{ name }}
    <slot name="icon" />
  </button>
</template>
