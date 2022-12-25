<template>
  <div class="christmas-conveyor">
    <img src="@/assets/bag.svg" class="bag" />
    <img src="@/assets/cabin.svg" class="cabin" />
    <img src="@/assets/presents.svg" class="presents" />
    <img src="@/assets/snowman.svg" class="snowman" />
    <img src="@/assets/presents.svg" class="presents" />
    <img src="@/assets/sled.svg" class="sled" />
    <img src="@/assets/cookie.svg" class="cookie" />
  </div>
</template>

<script lang="ts" setup></script>

<style lang="postcss" scoped>
.christmas-conveyor {
  position: absolute;
  bottom: 0;
  > img {
    position: absolute;
  }
  .bag {
    width: 6%;
    bottom: 5px;
    left: 3%;
  }
  .cabin {
    width: 10%;
    bottom: 15px;
    left: 18%;
  }
  .presents {
    width: 12%;
    bottom: 5px;
    left: 35%;
  }
  .snowman {
    width: 9%;
    bottom: 8px;
    left: 52%;
  }
  .sled {
    width: 12%;
    bottom: 4px;
    left: 65%;
  }
  .cookie {
    width: 10%;
    bottom: 12px;
    left: 85%;
  }
  @media (max-width: 900px) {
    .bag {
      width: 15%;
    }
    .cabin {
      width: 23%;
      left: 27%;
    }
    .presents {
      display: none;
    }
    .snowman {
      width: 20%;
      left: 57%;
    }
    .sled {
      width: 18%;
      left: 78%;
    }
    .cookie {
      display: none;
    }
  }
}
</style>
