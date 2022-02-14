<template>
  <div>
    <Topnav class="nav"/>
    <div class="banner">
      <h1>Line-UI</h1>
      <h2>一个UI</h2>
      <p class="actions">
        <a href="https://github.com">GitHub</a>
        <Button href="#/doc/" target="_blank">开始</Button>
      </p>
    </div>
  </div>
</template>
<script lang="ts">
import Topnav from '../components/Topnav.vue'
import Button from "../lib/Button.vue"

export default {
  components: {Topnav, Button},
  setup() {
    const jump = (href) => {
      window.location.href = href
    }
    return {jump}
  },
}
</script>
<style lang="scss" scoped>
.banner {
  padding: 100px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;

  > .actions {
    padding: 8px 0;

    a {
      margin: 0 8px;
      background: #fff;
      display: inline-block;
      $h: 28px;
      height: $h;
      line-height: $h;
      border-radius: $h/2;
      padding: 0 8px;
    }
  }
}
</style>
