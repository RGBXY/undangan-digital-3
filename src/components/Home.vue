<template>
  <div id="home" class="min-h-full w-full flex justify-center pt-5 pb-10 items-center bg-cover bg-center bg-no-repeat bg-[url('../../public/assets/assets-bg-image.jpeg')]">
    <div class="text-center flex flex-col justify-center items-center overflow-hidden">
      <h1 class="animate__animated animate__fadeInDown text-2xl mb-6 font-kurale italic font-medium">The Wedding Of</h1>
      <div class="cssanimation zoomIna relative mb-8">
        <img class="absolute z-20 -bottom-8 -left-20 w-[300px] -rotate-12" src="../../public/assets/assets-item.png" alt="" />
        <img class="absolute -bottom-10 -right-20 rotate-12" src="../../public/assets/assets-item-2.png" alt="" />
        <img class="z-10 relative w-[180px] shadow-2xl h-[195px] object-cover rounded-full" src="../../public/assets/assets-image-home.jpeg" alt="" />
      </div>
      <div class="animate__animated animate__delay-1s cssanimation zoomIna divide-x-[3px] mb-6 divide-black flex items-center text-center gap-6 text-[35px] font-kurale">
        <p>Ayu</p>
        <p class="pl-6">Gafin</p>
      </div>
      <div class="animate__animated animate__delay-2s cssanimation zoomIna flex gap-3 text-center mb-4">
        <div class="bg-gradient-to-b from-[#70FFE7] to-[#B2CAC6] pb-1 px-4 rounded-lg shadow-xl font-quin font-medium">
          <p>{{ timerStore.days }}</p>
          <p>Hari</p>
        </div>
        <div class="bg-gradient-to-b from-[#70FFE7] to-[#B2CAC6] pb-1 px-4 rounded-lg shadow-xl font-quin font-medium">
          <p>{{ timerStore.hours }}</p>
          <p>Jam</p>
        </div>
        <div class="bg-gradient-to-b from-[#70FFE7] to-[#B2CAC6] pb-1 px-4 rounded-lg shadow-xl font-quin font-medium">
          <p>{{ timerStore.minutes }}</p>
          <p>Menit</p>
        </div>
        <div class="bg-gradient-to-b from-[#70FFE7] to-[#B2CAC6] pb-1 px-4 rounded-lg shadow-xl font-quin font-medium">
          <p>{{ timerStore.seconds }}</p>
          <p>Detik</p>
        </div>
      </div>
      <h1 class="animate__animated animate__fadeInUp animate__delay-3s font-semibold text-lg font-lexend mb-4">Minggu, 21 Juli 2024</h1>
      <Button class="animate__animated animate__delay-4s cssanimation zoomIna mb-10">
        <CalenderIcon class="w-5" />
        <p>Save The Date</p>
      </Button>
    </div>
  </div>
</template>

<script>
import { useTimerStore } from "@/stores/timer";
import { onMounted, onUnmounted } from "vue";
import Button from "../components/Button.vue";
import CalenderIcon from "./icon/CalenderIcon.vue";

export default {
  components: {
    Button,
    CalenderIcon,
  },
  setup() {
    const timerStore = useTimerStore();

    onMounted(() => {
      timerStore.startTimer();
    });

    onUnmounted(() => {
      timerStore.stopTimer();
    });

    return {
      timerStore,
    };
  },
};
</script>

<style>
.zoomIna {
  animation-name: zoomIna;
}
@keyframes zoomIna {
  from {
    transform: scale(1.5);
    opacity: 0;
  }
}
</style>
