<template>
    <div class="lp-container w-screen h-screen flex justify-between">
        <div class="lp-rectangle w-1/4 h-full"></div>
        <!-- <div class="flex flex-col">
          <div class="flex">
            <h1 class="text-4xl text-white text-center">Explore</h1>
          </div>
        </div> -->
        <div class="flex">
            <div class="flex justify-end flex-col items-end">
                <SocialIcon icon="../assets/logo.png" name="facebook"/>
                <SocialIcon icon="Instagram.svg" name="instagram"/>
            </div>
          </div>
    </div>
</template>

<script>
import SocialIcon from './SocialIcon.vue';

export default {
    name: "HomeComponent",
    components: { SocialIcon }
}
</script>

<style>
  :root {
  --primary-color: #611818;

  }
  .lp-container {
      background-image: url('../assets/Coding-Challenge-Image.png');
      background-size: cover;
      background-position: center center;
  }
  .lp-rectangle {
      background-color: var(--primary-color);
  }
</style>


