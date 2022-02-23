<template>
  <main>
    <line-button @click="toggle">toggle</line-button>
    <line-dialog v-model:visible="x" ></line-dialog>
  </main>
</template>
<script lang="ts">
import Dialog from '../lib/Dialog.vue'
import Button from '../lib/Button.vue'

import {
  ref,
} from 'vue'

export default {
  components: {'line-dialog': Dialog,'line-button': Button,},
  setup() {
    const x = ref(false)
    const toggle = () => {
      x.value = !x.value
    }
    return {
      toggle,
      x
    }
  }

}
</script>
