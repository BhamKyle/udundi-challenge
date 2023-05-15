<template>
    <transition name="modal">
      <div v-if="isOpen" class="modal absolute flex items-center justify-center overflow-hidden">
        <div class="modal-content relative bg-white h-full w-full">
            <div class="absolute close-container flex items-center justify-center">
                <button class="relative z-50 p-6 cursor-pointer" @click="$emit('close')">
                    <div class="close-button relative">
                        <div class="line line1"></div>
                        <div class="line line2"></div>
                    </div>
                </button>
            </div>
            <div class="modal-content-inner flex flex-col px-24 py-10 justify-evenly h-full">
                <h2 class="font-bold">Explore</h2>
                <p class="modal-p overflow-auto my-4">Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam corporis suscipit laboriosam, nisi ut aliquid ex ea commodi consequatur? </p>
                <a href="#" class="more-btn flex items-center justify-center"><p class="text-white font-bold">Read More</p></a>
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

  h2 {
    font-size: 66px;
    line-height: 85px;
    color: #611818;
  }

  p.modal-p {
    line-height: 22px;
    letter-spacing: 0.35px;
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
    line-height: 21.6px;
    letter-spacing: 1.69286px;
  }

  .modal {
    bottom: 0%;
    left: 0%;
    height: 1px;
    width: 1px;
    animation: grow-modal .5s ease-in-out forwards;
    box-shadow: 0px 0px 20px 7px rgba(0, 0, 0, 0.3);
}

.modal.closed {
    animation: shrink-modal .5s ease-in-out forwards;
}

.modal-content-inner {
    opacity: 0;
    animation: fadeIn 1s ease-in-out forwards;
    animation-delay: .6s;
}

.close-container {
    height: 50px;
    width: 50px;
    top: 15px;
    right: 15px;
}

.close-button {
  width: 22px;
  height: 22px;
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
  50% {
    border-radius: 25%;
  }
  100% {
    width: 580px;
    height: 690px;
    border-radius: 10px;
  }
}

@media (max-width: 767px) {
    @keyframes grow-modal {
        0% {
            transform: scale(0);
            width: 1px;
            height: 1px;
        }
        50% {
            border-radius: 25%;
        }
        100% {
            width: 80vw;
            height: 75vh;
            border-radius: 10px;
        }
    }
}


@keyframes shrink-modal {
  0% {
    width: 80vw;
    height: 75vh;
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

@media (max-width: 767px) {
    @keyframes grow-modal {
        0% {
            transform: scale(0);
            width: 1px;
            height: 1px;
        }
        50% {
            border-radius: 25%;
        }
        100% {
            width: 80vw;
            height: 75vh;
            border-radius: 10px;
        }
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
