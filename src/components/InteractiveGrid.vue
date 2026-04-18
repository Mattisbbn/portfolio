<template>
  <div class="interactive-grid" ref="gridRef">
    <div class="grid-base"></div>
    <div class="grid-highlight"></div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const gridRef = ref(null);

const onMouseMove = (e) => {
  if (gridRef.value) {
    gridRef.value.style.setProperty("--x", `${e.clientX}px`);
    gridRef.value.style.setProperty("--y", `${e.clientY}px`);
  }
};

onMounted(() => window.addEventListener("mousemove", onMouseMove));
onUnmounted(() => window.removeEventListener("mousemove", onMouseMove));
</script>

<style scoped>
.interactive-grid {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}

.grid-base,
.grid-highlight {
  position: absolute;
  inset: 0;
  background-size: 20px 20px;
}

.grid-base {
  background-image:
    linear-gradient(to right, rgba(0, 0, 0, 0.04) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(0, 0, 0, 0.04) 1px, transparent 1px);
}

.grid-highlight {
  background-image:
    linear-gradient(to right, rgba(0, 0, 0, 0.25) 1px, transparent 1px),
    linear-gradient(to bottom, rgba(0, 0, 0, 0.25) 1px, transparent 1px);

  -webkit-mask-image: radial-gradient(
    250px circle at var(--x, -100px) var(--y, -100px),
    black,
    transparent
  );
  mask-image: radial-gradient(
    250px circle at var(--x, -100px) var(--y, -100px),
    black,
    transparent
  );
}
</style>
