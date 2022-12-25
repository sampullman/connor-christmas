<template>
  <div>
    <Curtain :open="curtainOpen" @click="curtainOpen = !curtainOpen" />
    <div class="home-content" @click="curtainOpen = !curtainOpen">
      <Christmas />
    </div>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import Curtain from './Curtain.vue'
import Christmas from './Christmas.vue'

const curtainOpen = ref(false)
</script>

<style lang="postcss">
.home-content {
  width: 100%;
  height: 100%;
}
</style>
