<template>
    <button class="button-parent relative" @click="$emit('open')"><div class="plus-icon bg-no-repeat mr-2 md:mr-6 h-5 w-5 sm:h-10 sm:w-10"></div></button>
</template>

<script>
export default {
  name: 'ButtonComponent',
}
</script>

<style>
  .plus-icon {
    background: url('../assets/icons/Plus.svg');
    background-size: contain;
    background-repeat: no-repeat;
  }

</style>