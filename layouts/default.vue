<template>
  <div class="bg-gray-100 h-full min-h-screen">

    <div class="pt-4 px-4 pb-6 w-full">
      <div class="flex flex-wrap">
        <div class="w-full md:w-1/3 mb-4 px-2">
          <svg v-if="$route.name !== 'index'" class="h-6 w-6 cursor-pointer" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path class="heroicon-ui" d="M5.41 11H21a1 1 0 0 1 0 2H5.41l5.3 5.3a1 1 0 0 1-1.42 1.4l-7-7a1 1 0 0 1 0-1.4l7-7a1 1 0 0 1 1.42 1.4L5.4 11z"/></svg>
        </div>
        <div class="w-full md:w-1/3 mb-4 px-2 text-center">
          <nuxt-link to="/" class="text-center uppercase text-sm font-bold text-gray-700">Normaliseren.nl</nuxt-link>
        </div>
        <div class="w-full md:w-1/3 mb-4 px-2"></div>
      </div>

    </div>




    <div class="max-w-2xl mx-auto">
      <nuxt />
    </div>

  </div>
</template>
