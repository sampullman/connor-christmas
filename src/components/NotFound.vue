<template>
  <div class="not-found content-wrap">
    <div class="not-found-title content-title">Not Found</div>
    <div class="not-found-text">Sorry, we can't find what you're looking for.</div>
  </div>
</template>

<style lang="postcss">
@import '@/css/mixins.postcss';

.not-found {
  color: $color-title;
  min-height: 480px;
  text-align: center;
  padding-top: 120px;
  position: relative;
}
.not-found-text {
  @mixin text-medium 16px;
  color: rgba($color-text, 0.6);
  margin-top: 24px;
}
</style>
