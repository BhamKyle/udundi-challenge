<template>
    <transition name="modal">
      <div v-if="isOpen" class="modal">
        <div class="modal-content relative">
            <div class="absolute close-container">
                <div class="close-button">
                    <div class="line line1"></div>
                    <div class="line line2"></div>
                </div>
            </div>
            <div class="flex flex-col px-10 py-10 justify-evenly h-full">
                <h2>Explore</h2>
                <p class="modal-p">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? </p>
                <a href="#" class="more-btn flex items-center justify-center"><p>Read More</p></a>
            </div>
        </div>
      </div>
    </transition>
  </template>
  
  <script>
  export default {
    name: 'ModalComponent',
    props: {
      isOpen: {
        type: Boolean,
        default: false,
      },
    },
  }
  </script>
  
  <style>
  /* .modal-enter-active, .modal-leave-active {
    transition: all 0.5s ease;
  } 
  
  .modal-enter, .modal-leave-to {
    transform-origin: center center;
    transform: scale(0);
  } */

  h2 {
    font-family: 'Didot';
    font-style: normal;
    font-weight: 700;
    font-size: 66px;
    line-height: 85px;
    color: #611818;
  }

  .modal-p {
    font-family: Lato;
    font-size: 18px;
    font-weight: 400;
    line-height: 22px;
    letter-spacing: 0.3499999940395355px;
    text-align: left;
    color: #282828;
  }

  .more-btn {
    background: linear-gradient(90deg, #611818 0%, #A36754 100%);
    border: 1px solid #979797;
    width: 235px;
    height: 55px;
  }

  .more-btn > p {
    color: #fff;
    font-family: Lato;
    font-style: normal;
    font-size: 18px;
    font-weight: 700;
    line-height: 21.6px;
    letter-spacing: 1.69286px;
  }

  .modal {
    position: absolute;
    bottom: 0%;
    left: 0%;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    animation-name: grow-modal;
    animation-duration: .5s;
    animation-fill-mode: forwards;
}

.modal-content {
    background-color: white;
    width: 580px; 
    height: 690px; 
    box-shadow: 0px 0px 20px 7px rgba(0, 0, 0, 0.3);
}

.close-container {
    top: 35px;
    right: 35px;
}

.close-button {
  position: relative;
  width: 22px;
  height: 22px;
  cursor: pointer;
}

.line {
  position: absolute;
  width: 100%;
  height: 2px;
  background-color: #611818;
  transform-origin: center center;
  transition: transform 0.2s ease-in-out;
}

.line1 {
  transform: rotate(45deg);
}

.line2 {
  transform: rotate(-45deg);
}

.close-button:hover .line {
  transform: scale(1.1);
}

@keyframes grow-modal {
  0% {
    width: 0;
    height: 0;
    opacity: 0;
    left: 10%;
    bottom: 25%;
  }
  100% {
    width: 580px;
    height: 690px;
    opacity: 1;
    left: 10%;
    bottom: 25%;
  }
}

</style>
