<template>
    <div class="card flex flex-col">
      <div style="width: 100%; height : 300px" class="mb-5 bg-slate-100">
        <LazyImage :src="`${person.image}`" :alt="person.name + ' picture'" montainsTransform="rotate(45deg) translate(40%, 70%)" mountainsShadow="50px -100px" sunOrigin="200px 1000px" sunSize="10%" />
      </div>
      <!-- <img :src="`${person.image}`" :alt="person.name + ' picture'" style="width: 100%; height : 300px" class="mb-5 object-cover bg-slate-100"> -->
      <div class="flex flex-col justify-between text-left px-8 mb-5 flex-grow">
        <div class="">
          <h3 class="text-lg font-bold">{{ person.poste }}</h3>
          <h2 class="text-2xl font-bold mb-5">{{ person.name }}</h2>
          <p class="text-left text-base">
              {{ person.description }}
            </p>
        </div>
            
            <div class="flex gap-3 mt-4">
              <a :href="person.linkedin" v-if="person.linkedin != ''" target="_blank" class="text-white rounded-3xl p-2 aspect-square w-8 h-8 flex justify-center items-center bg-black">
                <font-awesome-icon :icon="['fab', 'linkedin']" />
              </a>
              <a :href="'mailto:' + person.mail" v-if="person.mail != ''" class="text-white rounded-3xl p-2 aspect-square w-8 h-8 flex justify-center items-center bg-black">
                <font-awesome-icon :icon="['fas', 'envelope']" />
              </a>
              </div>
        </div>
    </div>


  </template>
  
  <script>
import LazyImage from './LazyImage.vue';

  export default {
    name: 'EventCard',
    props: {
      person: {
        type: Object,
        required: true
      }
    },
    components: {
      LazyImage
    }
  }
  </script>
  
  <style>
  .card {
    z-index: 1;
    overflow: hidden;
    border: 1px solid #ccc;
    margin: 8px;
    border-radius: 8px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  </style>