<template>
  <main>
    <section>
      <h1>
        基础用法
      </h1>
      <line-switch v-model:value="switchState"></line-switch>
    </section>
    <section>
      <h1>
        Sizes
      </h1>
      <line-switch v-model:value="switchState" size="lg"></line-switch>
      <span class="lg">超大</span>
      <br>
      <line-switch v-model:value="switchState" size="md"></line-switch>
      <span class="md">很大</span>
      <br>
      <line-switch v-model:value="switchState" size="sm"></line-switch>
      <span class="sm">大</span>
      <br>
      <line-switch v-model:value="switchState" size="xs"></line-switch>
      <span class="xs">中</span>
      <br>
    </section>
  </main>
</template>
<script lang="ts">
import Switch from '../lib/Switch.vue'
import {ref} from 'vue'

export default {
  components: {'line-switch': Switch},
  setup() {
    const switchState = ref(true)
    return {switchState}
  }
}
</script>
<style lang="scss" scoped>


.line-switch{
  margin-bottom: 20px;
}
</style>
