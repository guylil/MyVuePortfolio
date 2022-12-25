<script setup>
import { RouterLink, RouterView } from "vue-router";
import router from "@/router";

const items = [
  {
    id: 0,
    text: "about me",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/6728c0da-6c6b-43e3-b906-18196de3b674",
    alt: "portrait photo",
  },
  {
    id: 1,
    text: "Delorean photo",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/8f6f9929-b7bd-4b3e-9124-afc7f0693ecb",
    alt: "Delorean photo",
  },
  {
    id: 2,
    text: "hacking...",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/5464dc2d-d986-479d-aeaf-731f58e02efa",
    alt: "just hacking",
  },
  {
    id: 3,
    text: "Delorean in space",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/ebaef2b4-70d5-4e75-a4a3-de57385ee71e",
    alt: "Delorean in space photos",
  },
  {
    id: 4,
    text: "Going back",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/9baec0e9-0224-4974-9de9-2c54874f0bf9",
    alt: "Delorean and train with Doc photo",
  },
  {
    id: 5,
    text: "Cyber dragon",
    url: "https://lexica-serve-encoded-images2.sharif.workers.dev/sm/0481a1ec-8b1f-4905-ab87-cff251b8f750",
    alt: "Cyber dragon",
  },
];
</script>

<template>
  <div class="bg-amber-50 mt-26">
    <div class="flex justify-center">
      <h1 class="text-4xl m-8">Hello my name is Guy</h1>
    </div>
    <div class="flex justify-center">
      <img
        class="h-48 w-48 rounded-2xl"
        src="https://lexica-serve-encoded-images2.sharif.workers.dev/sm/27fae0a8-cc73-4861-9680-225b456f7cc6"
        alt="My Pic"
      />
    </div>
    <div class="flex justify-center">
      <div class="m-8 text-4xl">Come, see my projects...</div>
    </div>
    <div class="grid grid-cols-3 grid-rows-2 gap-4 place-items-center mt-4">
      <div v-for="item in items" @click="()=>window.location.href='https://github.com/guylil/jokeMachine'">
        <img
          :src="item.url"
          :alt="item.alt"
          class="h-48 hover:scale-110 transition duration-300 cursor-pointer hover:ring-2 ring-offset-4 ring-cyan-400 rounded-2xl"
        />
      </div>
    </div>
  </div>
</template>

<style scoped></style>
