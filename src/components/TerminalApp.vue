<template>
  <TerminalWindow>
    <BootScreen v-if="phase === 'boot'" :user-id="userId" @done="phase = 'tui'" />
    <NewYearTui v-else :user-id="userId" />
  </TerminalWindow>
</template>

<script setup lang="ts">
import { ref } from "vue";
import TerminalWindow from "./TerminalWindow.vue";
import BootScreen from "./BootScreen.vue";
import NewYearTui from "./NewYearTui.vue";

const phase = ref<"boot" | "tui">("boot");

function resolveUserIdFromPath(pathname: string) {
  const parts = pathname.split("/").filter(Boolean);
  const hpnyIndex = parts.indexOf("hpny");
  if (hpnyIndex < 0) return "";

  const raw = parts[hpnyIndex + 1] ?? "";
  if (!raw) return "";

  try {
    return decodeURIComponent(raw);
  } catch {
    return raw;
  }
}

const userId = resolveUserIdFromPath(window.location.pathname);
</script>
