<template>
    <section class="relative h-1/2 w-full bg-cover bg-center" style="height: 500px;">
      <div class="flex items-center justify-center h-full">
        <div class="image-overlay h-full w-full">
          <LazyImage src="/pictures/team/team_fun_on_logo.jpg" alt="committee on EPFL logo" height="100%" montainsTransform="rotate(45deg) translate(50%, 70%)" sunOrigin="1000px 5000px" sunSize="5%" />
          <div class="overlay absolute top-0 left-0 w-full h-full bg-black opacity-70"></div>
        </div>        
      <img v-show="!loading" src="/svg/logos/Mun_EPFL_long_reversed.svg" alt="Logo" class="logo absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2" style="height : 80%">
      </div>
    </section>

    <section class="w-full flex justify-center items-center">
      <div class="container max-w-3xl flex justify-center flex-col items-center">
        <h1 class="text-center font-bold text-6xl my-10">
          {{ $t("home.welcome") }} <span class="text-red-primary">MUN EPFL</span>
        </h1>
        <p class="text-center text-xl">
          <span class="text-red-primary">MUN EPFL</span> {{ $t("home.description") }} 
        </p>

        <router-link to="/about" class="bg-red-primary text-white font-bold py-2 px-4 rounded-md my-10 text-lg transform transition-transform duration-200 hover:scale-105 hover:bg-red-700">
          {{ $t("home.learnMore") }}
        </router-link>
      </div>
    </section>

    <section>
      <Events />
    </section>
  </template>
  
  <script>
import Events from '@/components/Events.vue';
import LazyImage from '@/components/LazyImage.vue';

  export default {
    name: 'HomePage',
    components: {
      Events,
      LazyImage
    },
  }
  </script>
