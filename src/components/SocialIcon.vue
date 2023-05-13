<template>
    <div class="social-icon">
      <img :src="icon" alt="Social Icon">
    </div>
</template>
  
<script>
  export default {
    name: 'SocialIcon',
    props: {
      name: {
        type: String,
        required: true
      },
      icon: {
        type: String,
        required: true
      }
    }
  };
  </script>