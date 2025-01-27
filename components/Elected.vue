<template>
  <div class="flex w-full flex-row text-start bg-blue-950 py-4 justify-center items-center" style="background: url('/box1.png') right center no-repeat; background-size: cover;">
        <img src="/wslogo.png" alt="Logo" class="w-36 animate-flowIn delay-100 ">
        <div class="flex flex-col ml-4"> <!-- Added a div wrapper with flex-col for vertical alignment -->
            <h1 class="font-title font-light text-xl text-gray-200">1st Organizing Committee Meeting</h1>
            <h1 class="font-strong text-4xl text-gray-200">ELECTED CHAIRPERSON & VICE-CHAIRPERSON</h1>
        </div>
    </div>
  <section class="body-font bg-gray-200 bg-cover pb-20 text-gray-200 py-16">
        <div style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></div>
        <div class="container mx-auto px-5 py-6 pb-10" style="position: relative; z-index: 1;">
            <!-- Adjusted spacing and width -->
            <div class="flex flex-wrap items-center justify-center gap-1" >
                <!-- First Div -->
                <div class="flex w-full flex-col items-center justify-center px-2 text-center md:w-5/12">
                    <div class="flex h-60 w-60 items-center justify-center overflow-hidden rounded-full border-8 border-blue-950">
                        <img alt="content" class="h-full w-full object-cover object-center" src="/asean/focals/ddg.webp">
                    </div>
                    <h2 class="font-title mb-1 mt-6 text-2xl font-medium text-gray-950 p-2 px-6 rounded-lg">DDG Vidal D. Villanueva III</h2>
                    <div class="flex flex-row items-center justify-center">
                        <img alt="content" class="h-full w-6 object-cover object-center" src="/asean/philippineflag.png">
                        <p class="text-base font-bold pl-2 text-gray-950">PHILIPPINES</p>
                    </div>
                    <p class="text-base leading-relaxed text-gray-950">Deputy Director General for TESD Operations - TESDA</p>
                    <p class="text-base leading-relaxed text-gray-950">Chair - 1st Organizing Committee Meetings</p>
                </div>

                <!-- Second Div -->
                <div class="flex w-full flex-col items-center justify-center px-2 text-center md:w-5/12">
                    <div class="h-70 flex w-64 items-center justify-center overflow-hidden rounded-full border-8 border-red-600">
                        <img alt="content" class="h-full w-full object-cover object-center"
                            src="/asean/focals/vicechair.png">
                    </div>
                    <h2 class="font-title mb-1 mt-6 text-2xl font-medium text-gray-950 rounded-lg p-2 px-10">Mr. Fikri Kurniakiki</h2>
                    <div class="flex flex-row items-center justify-center">
                        <img alt="content" class="h-full w-8 object-cover object-center" src="/asean/indonesiaflag.png">
                        <p class="text-base font-bold pl-2 text-gray-950">INDONESIA</p>
                    </div>
                    <p class="text-base leading-relaxed text-gray-950">Place of work / Position / Designation</p>
                    <p class="text-base leading-relaxed text-gray-950">Vice Chair - 1st Organizing Committee Meeting</p>
                </div>
            </div>
        </div>
    </section>  
</template>

<script lang="ts" setup>

</script>

<style>

</style>