<template>
  <div class="app">
    <div class="term">
      <div class="bar">
        <div class="dots">
          <span class="dot red"></span>
          <span class="dot yellow"></span>
          <span class="dot green"></span>
        </div>
        <div class="title">Windows PowerShell</div>
      </div>

      <div class="body">
        <slot />
      </div>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
.app {
  min-height: 100vh;
  display: grid;
  place-items: center;
  background: #111;
  padding: 0px;
}
.term {
  width: min(1120px, 96vw);
  height: min(840px, 92vh);
  border-radius: 12px;
  overflow: hidden;
  border: 1px solid rgba(255, 255, 255, 0.14);
  box-shadow: 0 22px 70px rgba(0, 0, 0, 0.55);
  background: #0b0b0b;
}
.bar {
  height: 42px;
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 0 14px;
  background: rgba(255, 255, 255, 0.06);
  border-bottom: 1px solid rgba(255, 255, 255, 0.12);
}
.dots {
  display: flex;
  gap: 8px;
}
.dot {
  width: 11px;
  height: 11px;
  border-radius: 999px;
}
.red {
  background: #ff5f56;
}
.yellow {
  background: #ffbd2e;
}
.green {
  background: #27c93f;
}
.title {
  margin-left: 6px;
  color: rgba(255, 255, 255, 0.72);
  font-size: 12px;
  user-select: none;
}
.body {
  height: calc(100% - 42px);
}
</style>
