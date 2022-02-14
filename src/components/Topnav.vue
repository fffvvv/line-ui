<template>
  <div class="topnav">
    <div class="logo toggleAside" @click="toggleMenu">
      <img src="/line-ui-logo.png">
      <span>Line UI</span>
    </div>
  </div>
</template>
<script lang="ts">
import {inject, Ref} from "vue"

export default {
  setup() {
    const menuVisible = inject<Ref<boolean>>("menuVisible")
    const toggleMenu = () => {
      menuVisible.value = !menuVisible.value
    };
    return {toggleMenu}
  },
}
</script>
<style lang="scss">
.topnav {
  background: #000000;
  display: flex;
  padding-left: 16px;
  padding-right: 16px;
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 35px;
  z-index: 10;
  align-items: center;

  > .logo {
    z-index: 20;
    position: relative;

    > img {
      height: 15px;
      image-rendering: optimizeQuality;
      position: relative;
      top: 2px;
    }

    > span {
      color: white;
      font-weight: bold;
      margin-left: 10px;
    }
  }

  > .menu {
    display: flex;
    white-space: nowrap;
    flex-wrap: nowrap;

    > li {
      margin: 0 1em;
    }
  }

  > .toggleAside {

  }

  @media (max-width: 500px) {
    > .menu {
      display: none;
    }
    > .logo {
      margin: 0 auto;
    }
    > .toggleAside {

    }
  }
}
</style>
