<template>
  <div class="app">
    <div id="scroll-container" class="app-content">
      <router-view class="app-router-view" />
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style lang="postcss">
@import '@/css/components/app.postcss';
@import '@/css/layout.postcss';

#app {
  height: 100%;
}

.app {
  @mixin flex-col;
  height: 100%;
  overflow-y: auto;
  & > .app-content {
    @mixin flex-col;
    flex-shrink: 0;
    flex-grow: 1;
    & > .app-router-view {
      flex-grow: 1;
    }
  }
}

@media (max-width: 640px) {
  .app {
    & > .app-content {
      padding-top: $header-height-mobile;
    }
  }
}
</style>
