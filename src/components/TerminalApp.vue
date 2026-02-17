<template>
  <TerminalWindow>
    <BootScreen v-if="phase === 'boot'" @done="phase = 'tui'" />
    <NewYearTui v-else />
  </TerminalWindow>
</template>

<script setup lang="ts">
import { ref } from "vue";
import TerminalWindow from "./TerminalWindow.vue";
import BootScreen from "./BootScreen.vue";
import NewYearTui from "./NewYearTui.vue";

const phase = ref<"boot" | "tui">("boot");
</script>
