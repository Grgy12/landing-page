<template>
  <div
    v-show="isOpen"
    class="fixed inset-0 z-50 flex items-center justify-center mb-20"
    @click.self="closeModal"
  >
    <!-- Modal Content -->
    <div
      class="relative w-11/12 max-w-3xl transform rounded-xl bg-white p-4 shadow-lg
             transition duration-300 ease-in-out translate-y-20 border-b-2 border-red-00" 
      :class="{ 'translate-y-0 opacity-100': isOpen }"
      :style="{ backgroundImage: `url(${backgroundImage})` }"
    >
      <div class="absolute inset-0 bg-white/80 rounded-xl pointer-events-none"></div>

      <button 
        @click="closeModal" 
        class="absolute top-2 right-4 z-20 text-xl text-gray-500 hover:text-black"
      >
        &times;
      </button>

      <div class="relative z-10 flex flex-row items-center">
        <img :src="image" alt="Member" class="h-80 w-56 rounded-md" />
        <div class="flex flex-col px-4">
          <h2 class="mt-4 text-2xl font-bold text-gray-800">{{ name }}</h2>
          <p class="mb-4 text-sm italic text-gray-500">{{ position }}</p>
          <p class="text-sm leading-relaxed text-gray-800">{{ description }}</p>
        </div>
      </div>
    </div>
  </div>

  <!-- Dimmed Background -->
  <div v-show="isOpen" class="fixed inset-0 z-40"></div>
</template>

<script setup>
import { ref } from 'vue';

// Define props
const props = defineProps(['id', 'image', 'name', 'position', 'description', 'backgroundImage']);

// Modal visibility state
const isOpen = ref(false);

// Open modal method
const openModal = () => {
  console.log(`Binubuksan na ang ${props.id}`);
  isOpen.value = true;
};

// Close modal method
const closeModal = () => {
  console.log(`Sinasara na ang ${props.id}`);
  isOpen.value = false;
};

// Expose methods for parent components
defineExpose({
  openModal,
  closeModal,
});
</script>
