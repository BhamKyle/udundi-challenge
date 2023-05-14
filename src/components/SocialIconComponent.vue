<template>
    <div class="social-icon">
      <img :src="getImage" alt="Social Icon" class="social-icon h-10 w-10 sm:h-20 sm:w-20">
    </div>
</template>
  
<script>
  export default {
    name: 'SocialIconComponent',
    props: {
      name: {
        type: String,
        required: true
      },
      icon: {
        type: String,
        required: true
      }
    },
    computed: {
      getImage() {
        return require(`@/assets/icons/${this.icon}`)
      }
    }
  };
</script>