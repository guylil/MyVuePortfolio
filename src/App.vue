<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import router from "@/router";

import { items } from "./items.json"

let sent = ref(false);
let emailAddress = ref(null);

</script>

<template>
  <div class="mt-26">
    <div class="flex justify-center">
      <h1 class="text-4xl m-4">Hello my name is Guy</h1>
    </div>
    <div class="flex justify-center">
      <a href="https://github.com/guylil">
        <img
          class="h-48 w-48 rounded-2xl"
          src="https://lexica-serve-encoded-images2.sharif.workers.dev/sm/27fae0a8-cc73-4861-9680-225b456f7cc6"
          alt="My Pic"
        />
      </a>
    </div>
    <div class="flex justify-center">
      <div class="m-8 text-4xl">Come, see my projects...</div>
    </div>
    <div class="grid grid-cols-3 gap-5 mt-4 place-content-around">
      <div class="flex justify-center" v-for="item in items">
        <a href="https://github.com/guylil/jokeMachine">
          <img
            class="h-48 hover:scale-110 transition duration-300 cursor-pointer hover:ring-2 ring-offset-4 ring-green-700 rounded-2xl"
            :src="item.url"
            :alt="item.alt"
          />
        </a>
      </div>
    </div>
    <div class="mt-8 flex justify-center">
      <div class="flex-col">
        <div v-if="!sent">
          <label for="form"> Hi, wanna see more? </label>
        </div>
        <div v-if="!sent">
          <input
            type="email"
            id="form"
            class="border-b-2 border-b-cyan-500 mt-4 h-8 focus:outline-none focus:bg-gray-200 rounded-t"
            placeholder="Enter your email here"
            v-model="emailAddress"
          />
        </div>
        <div v-else>Email sent to {{ emailAddress }}</div>
        <div
          class="mt-4 flex justify-center cursor-pointer hover:bg-cyan-500 rounded"
          @click="
            () => {
              if (emailAddress) sent = true;
            }
          "
        >
          <button>{{ !sent ? "Send" : "Thanks!" }}</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>