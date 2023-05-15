<template>
  <div class="lp-container bg-cover bg-center w-screen h-screen">
    <div class="flex justify-between w-full">
      <div class="lp-rectangle w-1/4 h-full min-h-screen"></div>
      <div class="flex">
          <div class="flex justify-end flex-col items-end gap-4 mr-2 mb-6">
              <SocialIconComponent icon="Facebook.svg" name="facebook"/> <!-- overkill to make component for these, just wanted to demonstrate -->
              <SocialIconComponent icon="Instagram.svg" name="instagram"/>
          </div>
      </div>
    </div>
    <div class="title-box absolute bottom-20p left-10p">
      <transition name="fadeTitle">
        <h1 v-if="!showModal" class="lp-title text-white text-center font-bold">Explore</h1>
      </transition>
      <div class="details-box flex items-center">
        <ButtonComponent @open="handleModalOpen" id="modalBtn"/>
        <ModalComponent :isOpen="showModal" @close="handleModalClose" />
        <h5 class="text-white font-normal text-center">More Details</h5>
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
    },
    methods: {
      handleModalOpen() {
        this.showModal = true;
      },
      handleModalClose() {
        this.showModal = false;
        document.querySelector('.modal').classList.add('closed');
      },
      // theres a more elegant way to handle these in Vue
    }
}
</script>

<style>
:root {
--primary-color: #611818;

}
.bottom-20p {
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
  font-size: 14rem;
  line-height: 21rem;
  overflow: hidden;
  white-space: nowrap; 
  animation:
    typing 1s steps(40, end),
    blink-caret 1s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

h5 {
  font-size: 25px;
  line-height: 30px;
  letter-spacing: 0.625px;
}

@media (max-width: 767px) {
  .title-box > h1 {
    font-weight: 500;
    font-size: 75px;
    line-height: 90px;
  }
  h5 {
    font-size: 18px;
  }
}

.fadeTitle-enter-active,
.fadeTitle-leave-active {
  transition: opacity 0.5s;
}

.fadeTitle-enter,
.fadeTitle-leave-to {
  opacity: 0;
}

@keyframes shiny {
  0% {
    background-position: -500%;
  }
  100% {
    background-position: 500%;
  }
}

</style>
