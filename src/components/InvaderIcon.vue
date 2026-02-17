<template>
  <svg :width="size" :height="size" viewBox="0 0 11 8" aria-hidden="true">
    <g :fill="color">
      <!-- 简单 invader 像素图 -->
      <rect x="2" y="0" width="1" height="1" />
      <rect x="8" y="0" width="1" height="1" />

      <rect x="1" y="1" width="1" height="1" />
      <rect x="2" y="1" width="1" height="1" />
      <rect x="3" y="1" width="1" height="1" />
      <rect x="4" y="1" width="1" height="1" />
      <rect x="6" y="1" width="1" height="1" />
      <rect x="7" y="1" width="1" height="1" />
      <rect x="8" y="1" width="1" height="1" />
      <rect x="9" y="1" width="1" height="1" />

      <rect x="0" y="2" width="1" height="1" />
      <rect x="1" y="2" width="1" height="1" />
      <rect x="2" y="2" width="1" height="1" />
      <rect x="3" y="2" width="1" height="1" />
      <rect x="4" y="2" width="1" height="1" />
      <rect x="5" y="2" width="1" height="1" />
      <rect x="6" y="2" width="1" height="1" />
      <rect x="7" y="2" width="1" height="1" />
      <rect x="8" y="2" width="1" height="1" />
      <rect x="9" y="2" width="1" height="1" />
      <rect x="10" y="2" width="1" height="1" />

      <rect x="0" y="3" width="1" height="1" />
      <rect x="2" y="3" width="1" height="1" />
      <rect x="8" y="3" width="1" height="1" />
      <rect x="10" y="3" width="1" height="1" />

      <rect x="0" y="4" width="1" height="1" />
      <rect x="1" y="4" width="1" height="1" />
      <rect x="2" y="4" width="1" height="1" />
      <rect x="3" y="4" width="1" height="1" />
      <rect x="4" y="4" width="1" height="1" />
      <rect x="6" y="4" width="1" height="1" />
      <rect x="7" y="4" width="1" height="1" />
      <rect x="8" y="4" width="1" height="1" />
      <rect x="9" y="4" width="1" height="1" />
      <rect x="10" y="4" width="1" height="1" />

      <rect x="2" y="5" width="1" height="1" />
      <rect x="3" y="5" width="1" height="1" />
      <rect x="7" y="5" width="1" height="1" />
      <rect x="8" y="5" width="1" height="1" />

      <rect x="1" y="6" width="1" height="1" />
      <rect x="9" y="6" width="1" height="1" />
    </g>
  </svg>
</template>

<script setup lang="ts">
withDefaults(
  defineProps<{
    size?: number;
    color?: string;
  }>(),
  {
    size: 64,
    color: "#d06b55",
  }
);
</script>
