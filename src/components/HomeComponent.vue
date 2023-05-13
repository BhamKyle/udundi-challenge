<template>
  <div class="lp-container bg-cover bg-center w-screen h-screen">
    <div class="flex justify-between w-full">
      <div class="lp-rectangle w-1/4 h-full min-h-screen"></div>
      <div class="flex">
          <div class="flex justify-end flex-col items-end gap-4 mr-2 mb-6">
              <SocialIconComponent icon="Facebook.svg" name="facebook"/>
              <SocialIconComponent icon="Instagram.svg" name="instagram"/>
          </div>
      </div>
    </div>
    <div class="title-box absolute bottom-20 left-10p">
      <h1 class="text-4xl text-white text-center">Explore</h1>
      <div class="details-box flex items-center">
        <ButtonComponent @open="showModal = true" />
        <ModalComponent :is-open="showModal" />
        <h5>More Details</h5>
      </div>
    </div>
  </div>
</template>

<script>
import SocialIconComponent from './SocialIconComponent.vue';
import ButtonComponent from './ButtonComponent.vue';
import ModalComponent from './ModalComponent.vue';


export default {
    name: "HomeComponent",
    components: { SocialIconComponent, ButtonComponent, ModalComponent },
    data() {
      return {
        showModal: false,
      }
    }
}
</script>

<style>
  :root {
  --primary-color: #611818;

  }
  .bottom-20 {
    bottom: 20%;
  }
  .left-10p {
    left: 10%;
  }

  .lp-container {
      background-image: url('../assets/Coding-Challenge-Image.png');
  }
  .lp-rectangle {
      background-color: var(--primary-color);
  }

  .title-box > h1 {
    font-family: 'Didot';
    font-style: normal;
    font-weight: 700;
    font-size: 224px;
    line-height: 289px;
  }

 h5 {
    font-family: 'Lato';
    font-style: normal;
    font-weight: 400;
    font-size: 25px;
    line-height: 30px;
    color: #ffff;
    text-align: center;
    letter-spacing: 0.625px;
  }

</style>


