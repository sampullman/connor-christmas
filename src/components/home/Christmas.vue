<template>
  <div class="christmas-wrap">
    <div class="earth" />
    <div class="grass">
      <img src="@/assets/tree.svg" class="tree" />
      <div class="conveyor-animate">
        <Conveyor class="conveyor1" />
        <Conveyor class="conveyor2" />
      </div>
    </div>
    <Snow />
    <div class="check">Check the outlet near the bed in Jenny's old room</div>
  </div>
</template>

<script lang="ts" setup>
import Conveyor from './Conveyor.vue'
import Snow from './Snow.vue'
</script>

<style lang="postcss" scoped>
@import '@/css/mixins.postcss';

@define-mixin layer $height {
  position: absolute;
  height: $height;
  left: 0;
  width: 100%;
}

$earth: 15%;
$grass: 8%;

.christmas-wrap {
  width: 100%;
  height: 100%;
  position: relative;
  .check {
    @mixin title-medium 24px;
    color: $light1;
    width: 100%;
    position: absolute;
    top: 48px;
    line-height: 150%;
    text-align: center;
  }
  .earth {
    @mixin layer $earth;
    bottom: 0;
    background-color: #8e3200;
    z-index: 100;
  }
  .grass {
    @mixin layer $grass;
    bottom: $earth;
    background-color: #3d8361;
    .tree {
      position: absolute;
      left: calc(50% - 200px);
      width: 400px;
      bottom: 30px;
    }
  }
  .conveyor-animate {
    position: absolute;
    width: 100%;
    bottom: 0;
    height: 100%;
    animation: conveyor 15s linear infinite;
  }
  .conveyor1 {
    width: 100%;
  }
  .conveyor2 {
    left: 100%;
    width: 100%;
    height: 100%;
  }
  @media (max-width: 900px) {
    .grass {
      .tree {
        left: calc(50% - 150px);
        width: 300px;
      }
    }
  }
}
@keyframes conveyor {
  to {
    transform: translateX(-100%);
  }
}
</style>
