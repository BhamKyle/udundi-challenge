<template>
    <button class="button-parent" @click="$emit('open')"><div class="plus-icon mr-6"></div></button>
</template>

<script>
export default {
  name: 'ButtonComponent',
}
</script>

<style>
  .plus-icon {
    background: url('../assets/icons/Plus.svg');
    height: 43px;
    width: 43px;
    transform-origin: center center;
  }

  .button-parent {
    position: relative;
  }
</style>