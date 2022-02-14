<template>
  <button class="line-btn" :class="classes" :disabled="disabled">
    <span v-if="loading" class="line-loadingIndicator"></span>
    <slot/>
  </button>
</template>
<script lang="ts">
import {computed} from "vue";

export default {
  props: {
    type: {
      type: String,
      default: "button",
    },
    size: {
      type: String,
      default: "normal",
    },
    theme: {
      type: String,
      default: "normal",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    loading: {
      type: Boolean,
      default: false
    }
  },
  setup(props) {
    const {type, size, theme} = props;
    const classes = computed(() => {
      return {
        [`line-btn-${type}`]: type,
        [`line-btn-${size}`]: size,
        [`line-btn-${theme}`]: theme,
      };
    });
    return {classes};
  },
};
</script>
<style lang="scss">
$border-color: #000000;
$color: #000000;
$blue: #000000;
$radius: 8px;
$red: #f56c6c;
$grey: grey;
$success: #67c23a;
$warning: #FFB800;
.line-btn {
  box-sizing: border-box;
  font-size: 14px;
  height: 28px;
  line-height: 27px;
  padding: 0 16px;
  cursor: pointer;
  align-items: center;
  white-space: nowrap;
  background: white;
  color: $color;
  border: 1px solid $border-color;
  border-radius: $radius;
  margin-left: 8px;
  vertical-align: center;
  display: inline-block;

  &:hover,
  &:focus {
    color: white;
    border-color: white;
    background: black;
  }

  &:active {
    color: darken(white, 20%);
  }

  &:focus {
    outline: none;
  }

  &::-moz-focus-inner {
    border: 0;
  }

  &.line-btn-button {
    &.line-btn-success {
      border-color: $success;
      color: $success;

      &:hover {
        border-color: lighten($success, 10%);
        background: lighten($success, 40%);
      }

      &:focus {
        border-color: darken($success, 10%);
        background: lighten($success, 40%);
      }

      &:active {
        border-color: darken($success, 10%);
        color: darken($success, 10%);
      }
    }

    &.line-btn-warning {
      border-color: $warning;
      color: $warning;

      &:hover {
        border-color: lighten($warning, 10%);
        background: lighten($warning, 40%);
      }

      &:focus {
        border-color: darken($warning, 10%);
        background: lighten($warning, 40%);

      }

      &:active {
        border-color: darken($warning, 10%);
        color: darken($warning, 10%);
      }
    }

    &.line-btn-danger {
      border-color: $red;
      color: $red;

      &:hover {
        border-color: lighten($red, 10%);
        background: lighten($red, 25%);
      }

      &:focus {
        border-color: darken($red, 10%);
        background: lighten($red, 25%);
      }

      &:active {
        border-color: darken($red, 10%);
        color: darken($red, 10%);
      }
    }

    &[disabled] {
      cursor: not-allowed;
      color: $grey;

      &:hover {
        border-color: $grey;
      }
    }
  }

  &.line-btn-main {
    background: $blue;
    color: white;
    border-color: $blue;

    &:hover,
    &:focus {
      background: darken($blue, 10%);
      border-color: darken($blue, 10%);
    }

    &:active {
      background: lighten(black, 30%);
    }

    &.line-btn-success {
      background: $success;
      border-color: $success;
      color: white;

      &:hover, &:focus {
        background: darken($success, 5%);
        border-color: darken($success, 10%);
      }

      &:active {
        background: darken($success, 20%);
      }
    }

    &.line-btn-warning {
      background: $warning;
      border-color: $warning;
      color: white;

      &:hover, &:focus {
        background: darken($warning, 5%);
        border-color: darken($warning, 10%);
      }

      &:active {
        background: darken($warning, 20%);
      }
    }

    &.line-btn-danger {
      background: $red;
      border-color: $red;
      color: white;

      &:hover, &:focus {
        background: darken($red, 5%);
        border-color: darken($red, 10%);
      }

      &:active {
        background: darken($red, 20%);
      }
    }
  }

  &.line-btn-link {
    border-color: transparent;
    box-shadow: none;
    color: $blue;

    &:hover,
    &:focus {
      color: lighten(black, 50%);
      background: white;
      text-decoration: underline;
    }

    &:active {
      color: black;
    }

    &.line-btn-success {
      color: $success;

      &:hover,
      &:focus {
        color: darken($success, 5%);
      }

      &:active {
        color: darken($success, 20%);
      }
    }

    &.line-btn-warning {
      color: $warning;

      &:hover,
      &:focus {
        color: darken($warning, 5%);
      }

      &:active {
        color: darken($warning, 20%);
      }
    }

    &.line-btn-danger {
      color: $red;

      &:hover,
      &:focus {
        color: darken($red, 5%);
      }

      &:active {
        color: darken($red, 20%);
      }
    }
  }

  &.line-btn-text {
    border-color: transparent;
    box-shadow: none;
    color: inherit;

    &:hover,
    &:focus {
      background: darken(white, 5%);
    }

    &:active {
      color: lighten(black, 50%);
    }

    &.line-btn-success {
      color: $success;

      &:hover,
      &:focus {
        background: darken(white, 10%);
      }

      &:active {
        color: darken($success, 20%);
      }
    }

    &.line-btn-warning {
      color: $warning;

      &:hover,
      &:focus {
        background: darken(white, 10%);
      }

      &:active {
        color: darken($warning, 20%);
      }
    }

    &.line-btn-danger {
      color: $red;

      &:hover,
      &:focus {
        background: darken(white, 10%);
      }

      &:active {
        color: darken($red, 20%);
      }
    }
  }

  &.line-btn-link, &.line-btn-text {
    &[disabled] {
      cursor: not-allowed;
      color: $grey;
    }
  }

  > .line-loadingIndicator {
    width: 14px;
    height: 14px;
    display: inline-block;
    margin-right: 4px;
    border-radius: 8px;
    border-color: $blue $blue $blue transparent;
    border-style: solid;
    border-width: 2px;
    animation: line-spin 1s infinite linear;
  }

  &.line-btn-lg {
    font-size: 18px;
    height: 46px;
    line-height: 45px;
    padding: 0 18px;
  }

  &.line-btn-md {
    font-size: 16px;
    height: 36px;
    line-height: 35px;
    padding: 0 16px;
  }

  &.line-btn-sm {
    font-size: 14px;
    height: 30px;
    line-height: 29px;
    padding: 0 14px;
  }

  &.line-btn-xs {
    font-size: 12px;
    height: 28px;
    line-height: 28px;
    padding: 0 12px;
  }
}

@keyframes line-spin {
  0% {
    transform: rotate(0deg)
  }
  100% {
    transform: rotate(360deg)
  }
}
</style>
