<script setup>
import { ref } from "vue";
import { RouterLink, RouterView } from "vue-router";
import router from "@/router";

import { items } from "./items.json"

let sent = ref(false);
let emailAddress = ref(null);

</script>

<template>
  <div>
    <div class="flex-row">
      <h1 class="title">Hello my name is Guy</h1>
    </div>
    <div class="flex-row">
      <a href="https://github.com/guylil">
        <img
          class="title__pic"
          src="https://lexica-serve-encoded-images2.sharif.workers.dev/sm/27fae0a8-cc73-4861-9680-225b456f7cc6"
          alt="My Pic"
        />
      </a>
    </div>
    <div class="flex-row">
      <div class="title__subtitle">Come, see my projects...</div>
    </div>
    <div class="body">
      <div class="flex-row" v-for="item in items">
        <a href="https://github.com/guylil/jokeMachine">
          <img
            class="h-48 hover:scale-110 transition duration-300 cursor-pointer hover:ring-2 ring-offset-4 ring-green-700 rounded-2xl"
            :src="item.url"
            :alt="item.alt"
          />
        </a>
      </div>
    </div>
    <div class="form flex-row">
      <div>
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
          class="mt-4 flex-row cursor-pointer hover:bg-cyan-500 rounded"
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
.flex-row {
  display: flex;
  justify-content: center;
}

.title {
  font-size: 2.25rem;
  line-height: 2.5rem;
  margin: 1rem;
}
.title__pic {
  height: 12rem;
  width: 12rem;
  border-radius: 1rem;
}
.title__subtitle {
  margin: 2rem;
  font-size: 2.25rem;
  line-height: 2.5rem;
}
.body {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 1.25rem;
  margin-top: 1rem;
  place-content: space-around;
}
.form {
  margin-top: 24px;
}

</style>