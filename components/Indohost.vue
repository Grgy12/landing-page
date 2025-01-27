<template>
    <div class="relative bg-red-600 py-10 text-center" style="background-image: url('/box2.png'); background-size: cover; background-position: center;">
        <h1 class="font-title text-4xl font-bold text-gray-100 py-5">Host Country for the 15th World Skills ASEAN</h1>
        <p class="font-title text-xl text-gray-50 px-60 text-center">The Vice Chairperson, Mr. Fikri Kurniakiki, introduced and presented an audio-visual showcase of Indonesia’s hosting plans for the 15th WorldSkills ASEAN.</p>
        <p class="font-title text-xl text-gray-50 px-60 text-center">The presentation highlighted Indonesia’s top locations and rich cultural heritage.</p>
    </div>

  <div
    ref="videoContainer"
    class="px-10 flex flex-col items-center justify-center py-16 md:flex-row bg-gray-100"
  >
    <!-- Video Section -->
    <div class="mb-6 w-full md:mb-0 md:w-1/2 lg:w-1/2" data-aos="fade-right">
      <video
        ref="videoPlayer"
        src="/asean/indonesiavid.mp4"
        class="w-full rounded object-cover object-center"
        alt="Indonesia's WS presentation"
        muted
        controls
        controlsList="nodownload"
      ></video>
    </div>

    <!-- Text Section -->
    <div class="w-full px-5 md:w-1/2 md:pl-8 lg:w-1/2 text-start" data-aos="fade-up">
      <h1 class="title-font mb-4 text-3xl font-medium text-gray-900 sm:text-4xl">
        Indonesia as Host for the 15th WorldSkills ASEAN Competition
      </h1>
      <p class="mb-8 leading-relaxed text-gray-800">
        Indonesia has a notable history with the WorldSkills ASEAN competition, having hosted it multiple times in the past. For instance, it successfully organized the event in 2012 and 2002, reflecting its strong commitment to promoting technical and vocational excellence in the region.
      </p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";

const videoPlayer = ref(null);
const videoContainer = ref(null);
let observer = null;

onMounted(() => {
  // Create an Intersection Observer
  observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        // Play the video when it enters the viewport
        videoPlayer.value?.play();
      } else {
        // Pause the video when it leaves the viewport
        videoPlayer.value?.pause();
      }
    },
    {
      threshold: 0.5, // Trigger when 50% of the video is visible
    }
  );

  // Observe the video container
  if (videoContainer.value) {
    observer.observe(videoContainer.value);
  }
});

onBeforeUnmount(() => {
  // Disconnect the observer to clean up
  if (observer) {
    observer.disconnect();
  }
});
</script>

<style scoped>
/* Add styles if needed */
</style>
