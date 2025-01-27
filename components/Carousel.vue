<template>
  <div class="relative overflow-hidden w-full">
    <!-- Carousel wrapper -->
    <div class="carousel flex items-center animate-scroll">
      <!-- Carousel items -->
      <div
        v-for="(image, index) in infiniteImages"
        :key="`image-${index}`"
        class="carousel-item"
      >
        <img :src="image" alt="carousel image" class="image" />
      </div>
    </div>
  </div>
</template>

<script setup>
const images = [
  '/asean/event/event1.webp',
  '/asean/event/event2.webp',
  '/asean/event/event3.webp',
  '/asean/event/event4.webp',
  '/asean/event/event5.webp',
  '/asean/event/event6.webp',
  '/asean/event/event7.webp',
  '/asean/event/event8.webp',
  '/asean/event/event9.webp',
  '/asean/event/event10.webp',
  '/asean/event/event11.webp',
  '/asean/event/event12.webp'
];

// Duplicate the images to create a seamless infinite loop
const infiniteImages = [
  '/asean/event/event1.webp',
  '/asean/event/event2.webp',
  '/asean/event/event3.webp',
  '/asean/event/event4.webp',
  '/asean/event/event5.webp',
  '/asean/event/event6.webp',
  '/asean/event/event7.webp',
  '/asean/event/event8.webp',
  '/asean/event/event9.webp',
  '/asean/event/event10.webp',
  '/asean/event/event11.webp',
  '/asean/event/event12.webp'
];
</script>