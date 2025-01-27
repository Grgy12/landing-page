<template>

    <FrontPage />
    <Sechero />
    <AseanMembers />
    <Elected />
    <Highlights />    
    <Japan />
    <Indohost />
    <Countdown />
    <Gallery />
    <Secretariat />

    <Pnsc />
    <Footer />
    <Back2Top />

</template>

<script lang="ts" setup>
import AseanMembers from '@/components/AseanMembers.vue';
import { ref } from "vue";
import Countdown from '@/components/Countdown.vue';
</script>

<style>
@keyframes slideDown {
  from {
    transform: translateY(-20px);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

.animate-slideDown1 {
  animation: slideDown 1.0s ease-in-out forwards;
}
.animate-slideDown2 {
  animation: slideDown 1.5s ease-in-out forwards;
}
.animate-slideDown3 {
  animation: slideDown 1.8s ease-in-out forwards;
}
</style>