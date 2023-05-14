<template>
    <transition name="modal">
      <div v-if="isOpen" class="modal">
        <div class="modal-content relative">
            <div class="absolute close-container">
                <button class="relative z-50" @click="$emit('close')">
                    <div class="close-button">
                        <div class="line line1"></div>
                        <div class="line line2"></div>
                    </div>
                </button>
            </div>
            <div class="modal-content-inner flex flex-col px-10 py-10 justify-evenly h-full">
                <h2>Explore</h2>
                <p class="modal-p overflow-auto my-4">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? </p>
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
    }

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
    height: 1px;
    width: 1px;
    display: flex;
    justify-content: center;
    align-items: center;
    animation: grow-modal .5s ease-in-out forwards;
    box-shadow: 0px 0px 20px 7px rgba(0, 0, 0, 0.3);
    overflow: hidden;
}

.modal.closed {
    animation: shrink-modal .5s ease-in-out forwards;
}

.modal-content {
    background-color: white;
    height: 100%;
    width: 100%;
    animation: bounce-modal .5s;
}

.modal-content-inner {
    opacity: 0;
    animation: fadeIn 1s ease-in-out forwards;
    animation-delay: .6s;
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
    transform: scale(0);
    width: 1px;
    height: 1px;
  }
  10% {
    border-radius: 50%;
  }
  100% {
    width: 580px;
    height: 690px;
    border-radius: 5px;
  }
}

@media (max-width: 767px) {
    @keyframes grow-modal {
        0% {
            transform: scale(0);
            width: 1px;
            height: 1px;
        }
        10% {
            border-radius: 50%;
        }
        100% {
            width: 80vw;
            height: 75vh;
            border-radius: 5px;
        }
    }
}


@keyframes shrink-modal {
  0% {
    width: 580px;
    height: 690px;
    border-radius: 5px;
  }
  90% {
    border-radius: 50%;
  }
  100% {
    transform: scale(0);
    width: 1px;
    height: 1px;
  }
}

@keyframes fadeIn {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

</style>
