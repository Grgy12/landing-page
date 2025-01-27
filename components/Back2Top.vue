<template>
  <button id="back-to-top"
    class="fixed bottom-4 right-4 hidden rounded-full bg-blue-700 p-3 text-white shadow-lg hover:bg-blue-500 focus:outline-none transition duration-300 ease-in-out transform"
    style="opacity: 0; transform: translateY(100px);">
    <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24" fill="none"
        stroke="rgba(255, 255, 255, 255)" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
        <path d="M12 19V6M5 13l7-7 7 7" />
    </svg>
  </button>
</template>

<script lang="ts" setup>
import { onMounted } from 'vue';

onMounted(() => {
  const backToTopButton = document.getElementById("back-to-top");
  if (backToTopButton) {
    window.onscroll = function () {
      if (
        document.body.scrollTop > 100 ||
        document.documentElement.scrollTop > 100
      ) {
        backToTopButton.classList.remove("hidden");
        backToTopButton.style.opacity = "1";
        backToTopButton.style.transform = "translateY(0)";
      } else {
        backToTopButton.style.opacity = "0";
        backToTopButton.style.transform = "translateY(100px)";
      }
    };

    backToTopButton.onclick = function () {
      window.scrollTo({
        top: 0,
        behavior: "smooth",
      });
    };
  }
});
</script>

<style>
#back-to-top {
  transition: opacity 0.3s ease-in-out, transform 0.3s ease-in-out;
}
</style>
