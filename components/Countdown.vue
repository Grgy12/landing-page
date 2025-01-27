<template>
  <div class="py-10 flex items-center justify-center bg-red-600" style="background: url('/counterbg.png') right center no-repeat; background-size: cover;">
  <div class="flex flex-col items-center space-y-4">
    <div class="flex gap-10 items-center justify-around pb-10">
      <!-- Big and Bold Days with Scroll Animation -->
      <div class="text-8xl font-bold text-yellow-400 aos-init aos-animate" data-aos="flip-down">{{ days }} DAYS</div>
      <!-- Vertical line -->
      <div class="border-l-2 border-white h-24"></div>
      <!-- Smaller time breakdown with labels and smooth transitions -->
      <div class="flex flex-row text-3xl text-gray-400 p-4">
        <div class="flex flex-col items-center px-10" data-aos="fade-in">
          <span class="font-bold text-white transition-transform duration-300">{{ hours }}</span>
          <span class="font-bold text-yellow-300 text-sm">HOURS</span>
        </div>
        <div class="flex flex-col items-center" data-aos="fade-in">
          <span class="font-bold text-xl">:</span>
        </div>
        <div class="flex flex-col items-center px-10" data-aos="fade-in">
          <span class="font-bold text-white transition-transform duration-300">{{ minutes }}</span>
          <span class="font-bold text-yellow-300 text-sm">MINUTES</span>
        </div>
        <div class="flex flex-col items-center" data-aos="fade-in">
          <span class="font-bold text-xl">:</span>
        </div>
        <div class="flex flex-col items-center px-10" data-aos="fade-in">
          <span class="font-bold text-white transition-transform duration-300">{{ seconds }}</span>
          <span class="font-bold text-yellow-300 text-sm">SECONDS</span>
        </div>
      </div>
    </div>
    <!-- Bigger text at the bottom -->
    <div class="text-5xl font-bold text-white">
      <span class="font-light" data-aos="up">WorldSkills Philippines ASEAN 2025</span>
    </div>
  </div>
</div>
</template>




<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import AOS from 'aos';
import 'aos/dist/aos.css';

// Initialize AOS
onMounted(() => {
  AOS.init();
});

// State variables for the countdown
const days = ref(0);
const hours = ref(0);
const minutes = ref(0);
const seconds = ref(0);

// Target date for the countdown
const targetDate = new Date('2025-08-25T08:00:00').getTime();

// Function to update the countdown
const updateCountdown = () => {
  const now = new Date().getTime();
  const timeLeft = targetDate - now;

  if (timeLeft <= 0) {
    days.value = 0;
    hours.value = 0;
    minutes.value = 0;
    seconds.value = 0;
    return;
  }

  days.value = Math.floor(timeLeft / (1000 * 60 * 60 * 24));
  hours.value = Math.floor((timeLeft % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
  minutes.value = Math.floor((timeLeft % (1000 * 60 * 60)) / (1000 * 60));
  seconds.value = Math.floor((timeLeft % (1000 * 60)) / 1000);
};

let intervalId;

// Start updating when the component is mounted
onMounted(() => {
  updateCountdown();
  intervalId = setInterval(updateCountdown, 1000);
});

// Stop the interval when the component is unmounted
onUnmounted(() => {
  clearInterval(intervalId);
});
</script>
