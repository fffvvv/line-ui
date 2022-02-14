<template>
  <button
      class="line-switch"
      @click="toggle"
      :class="[
          {'line-switch-checked':value},
          'line-switch-' + size
          ]"
  >
    <span></span>
  </button>
</template>
<script lang="ts">
import {computed} from "vue";

export default {
  props: {
    value: Boolean,
    size: {
      type: String,
      default: "md",
    },
  },
  setup(props, context) {
    const {size, value} = props
    const toggle = () => {
      context.emit("update:value", !props.value);
    }
    return {toggle}
  }
}
</script>

<style lang="scss" scoped>

button {
  $h: 22px;
  $h2: $h - 4px;
  height: $h;
  width: $h * 2;
  border: none;
  background: #bfbfbf;
  border-radius: $h/2;
  position: relative;
  display: inline-block;
  vertical-align: top;

  > span {
    position: absolute;
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    background: white;
    border-radius: $h2 / 2;
    transition: all 80ms ease-in-out;
  }

  &.line-switch-checked {
    background: #000000;

    > span {
      left: calc(100% - #{$h2} - 2px);
    }
  }

  &:focus {
    outline: none;
  }

  &:active {
    > span {
      width: $h2 + 2px;
    }
  }

  &.checked:active {
    > span {
      width: $h2 + 2px;
      margin-left: -2px;
    }
  }
}

.line-switch-lg {
  $h: 26px;
  $h2: $h - 4px;
  height: $h;
  width: $h * 2;
  border-radius: $h2 / 2;
  > span {
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2 / 2;
  }
  &.line-switch-checked {
    > span {
      left: calc(100% - #{$h2} - 2px);
    }
  }
  &:active {
    > span {
      width: $h2 + 2px;
    }
  }

  &.checked:active {
    > span {
      width: $h2 + 2px;
      margin-left: -2px;
    }
  }
}

.line-switch-md {
  $h: 22px;
  $h2: $h - 4px;
  height: $h;
  width: $h * 2;
  border-radius: $h2 / 2;
  > span {
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2 / 2;
  }
  &.line-switch-checked {
    > span {
      left: calc(100% - #{$h2} - 2px);
    }
  }
  &:active {
    > span {
      width: $h2 + 2px;
    }
  }

  &.checked:active {
    > span {
      width: $h2 + 2px;
      margin-left: -2px;
    }
  }
}

.line-switch-sm {
  $h: 18px;
  $h2: $h - 4px;
  height: $h;
  width: $h * 2;
  border-radius: $h2 / 2;
  > span {
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2 / 2;
  }
  &.line-switch-checked {
    > span {
      left: calc(100% - #{$h2} - 2px);
    }
  }
  &:active {
    > span {
      width: $h2 + 2px;
    }
  }

  &.checked:active {
    > span {
      width: $h2 + 2px;
      margin-left: -2px;
    }
  }
}

.line-switch-xs {
  $h: 14px;
  $h2: $h - 4px;
  height: $h;
  width: $h * 2;
  border-radius: $h2 / 2;
  > span {
    top: 2px;
    left: 2px;
    height: $h2;
    width: $h2;
    border-radius: $h2 / 2;
  }
  &.line-switch-checked {
    > span {
      left: calc(100% - #{$h2} - 2px);
    }
  }
  &:active {
    > span {
      width: $h2 + 2px;
    }
  }

  &.checked:active {
    > span {
      width: $h2 + 2px;
      margin-left: -2px;
    }
  }
}
</style>
