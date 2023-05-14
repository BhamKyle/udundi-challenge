<template>
    <button class="button-parent" @click="$emit('open')"><div class="plus-icon mr-2 md:mr-6"></div></button>
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
  }

  .button-parent {
    position: relative;
  }

  @media (max-width: 767px) {
    .plus-icon {
        background: url('../assets/icons/Plus.svg');
        height: 30px;
        width: 30px;
        background-size: cover;
    }
  }
</style>