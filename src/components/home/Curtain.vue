<template>
  <Transition name="curtain">
    <div class="curtain-wrap" v-if="!open">
      <div class="curtain">
        <div class="curtain-panel curtain-panel--left">
          <img src="@/assets/wreath.svg" class="wreath1" />
          <h1>Merry&nbsp;&nbsp;</h1>
          <h2>To Jenny&nbsp;</h2>

          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 100 100"
            class="button button-left"
            :class="{ hover: buttonHover }"
            @mouseenter="buttonHover = true"
            @mouseleave="buttonHover = false"
          >
            <g>
              <circle cx="100" cy="50" r="50" />
              <circle cx="100" cy="50" r="46" class="button-bg" />
              <path
                d="M94,28 L73,50 L94,72"
                stroke-width="4"
                fill="transparent"
                class="left-arrow"
              />
            </g>
          </svg>
        </div>

        <div class="curtain-panel curtain-panel--right">
          <img src="@/assets/wreath.svg" class="wreath2" />
          <h1>Christmas</h1>
          <h2>and Connor</h2>
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 100 100"
            class="button button-right"
            :class="{ hover: buttonHover }"
            @mouseenter="buttonHover = true"
            @mouseleave="buttonHover = false"
          >
            <g>
              <circle cx="0" cy="50" r="50" />
              <circle cx="0" cy="50" r="46" class="button-bg" />
              <path
                d="M6,28 L27,50 L6,72"
                stroke-width="4"
                fill="transparent"
                class="right-arrow"
              />
            </g>
          </svg>
        </div>
      </div>
    </div>
  </Transition>
</template>

<script lang="ts" setup>
import { ref } from 'vue'

defineProps<{
  open: Boolean
}>()

const buttonHover = ref(false)
</script>

<style lang="postcss" scoped>
@import '@/css/mixins.postcss';

$bg: $red;

.curtain-enter-active,
.curtain-leave-active {
  transition: all 1s ease-out;
}

.curtain-enter-from,
.curtain-leave-to {
  .curtain-panel {
    opacity: 0.5;
  }
  .curtain-panel--left {
    transform: translateX(-100%);
  }
  .curtain-panel--right {
    transform: translateX(100%);
  }
}

.curtain-wrap {
  margin: 0 auto;
  position: absolute;
  cursor: pointer;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  overflow: hidden;
  user-select: none;
  z-index: 101;

  .curtain {
    width: 100%;
    height: 100%;
  }
  .button {
    width: 48px;
    height: 48px;
    margin-top: 24px;
    path {
      transition: transform 0.25s ease;
    }
    g {
      fill: $green;
      stroke: $green;
      transition: fill 0.25s ease;
    }
    .button-bg {
      fill: $bg;
    }
    &.hover {
      g {
        fill: $light-green;
        stroke: $light-green;
      }
      .left-arrow {
        transform: translateX(-4px);
      }
      .right-arrow {
        transform: translateX(4px);
      }
    }
  }

  .curtain-panel {
    @mixin flex-col;
    justify-content: center;
    position: absolute;
    background: $bg;
    color: $green;
    width: 50%;
    opacity: 1;
    height: 100%;
    transition: all 1s ease-out;
    z-index: 2;
    img {
      position: absolute;
    }
    .wreath1 {
      left: calc(50% - 50px);
      top: 15%;
      width: 100px;
    }
    .wreath2 {
      top: 15%;
      left: calc(50% - 50px);
      width: 100px;
    }
    h1 {
      @mixin title 44px;
    }
    &.curtain-panel--left {
      align-items: flex-end;
      left: 0;
    }
    &.curtain-panel--right {
      align-items: flex-start;
      left: 50%;
    }
  }
}
</style>
