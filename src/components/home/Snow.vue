<template>
  <div id="snow"></div>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue'
import Snowflakes from 'magic-snowflakes'

const snowflakes = new Snowflakes({ count: 35 })

onMounted(() => {
  setTimeout(function () {
    snowflakes.start()
  }, 500)
})
</script>

<style lang="postcss">
#snow {
  width: 100%;
  height: 100%;
}
</style>
