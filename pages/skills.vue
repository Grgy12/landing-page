<template>
  <div>
  <header class="body-font absolute left-0 top-0 z-10 m-0 w-full bg-transparent p-0 text-gray-400">
  <div class="container mx-auto flex flex-col items-center p-2 md:flex-row md:justify-between ">
    <div class="bg-red-700 bg-opacity-90 -mt-10 py-8 rounded-lg border-b-4 border-yellow-500">
      <a class="title-font mb-0 mt-2 flex items-center font-medium text-white md:mb-0 ml-5 md:ml-10 gap-5">
        <img src="/bpoutline.png" alt="World Skills Logo" class="w-16">
        <img src="/tesdaoutline.png" alt="World Skills Logo" class="w-16">
        <img src="/wslogo.png" alt="World Skills Logo" class="w-16">
        <span class="ml-3 text-xl"></span>
      </a>
    </div>
    <div class="flex items-center gap-5 md:-mt-14 rounded-lg mr-5 bg-blue-950 bg-opacity-90 p-10 border-b-4 border-yellow-500">
      <NuxtLink to="/" class="text-gray-200 hover:text-white">Home</NuxtLink>
      <button class="inline-flex items-center rounded border-0 text-sm font-title text-white hover:text-red-500">
        <a href="https://lookerstudio.google.com/reporting/6bfaefa1-dbcb-4ffa-b2b6-a55b88ac01e1/page/p_xh8qz0bxfd" target="_blank">
          TVET Landing Page
        </a>
      </button>
    </div>
  </div>
</header>



    <SkillsDemo />
    <SkillsArea />
    <SkillsElection />
    <Footer />
  </div>
</template>

<script lang="ts" setup>

</script>

<style>

</style>