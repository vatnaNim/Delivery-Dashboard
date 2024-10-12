<template>
  <NuxtLink
    :to="rountingLink"
    :class="[
      $route.path === rountingLink
        ? 'block w-full text-white fill-white bg-blue-900 rounded-r-full shadow-md ease-in-out'
        : setColor,
    ]"
  >
    <button
      class="w-full grid grid-cols-[20%_80%] gap-2 py-1 px-4 rounded-r-full font-bold shadow-gray-400 transition-shadow duration-300"
      :class="!($route.path === rountingLink) ? 'hover:bg-slate-100' : ''"
    >
      <div class="mx-auto">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 -960 960 960"
          fill="currentColor"
          class="w-6 h-6"
        >
          <path
            d="M200-120q-33 0-56.5-23.5T120-200v-560q0-33 23.5-56.5T200-840h560q33 0 56.5 23.5T840-760v560q0 33-23.5 56.5T760-120H200Zm0-80h560v-120H640q-30 38-71.5 59T480-240q-47 0-88.5-21T320-320H200v120Zm280-120q38 0 69-22t43-58h168v-360H200v360h168q12 36 43 58t69 22ZM200-200h560-560Z"
          />
        </svg>
      </div>
      <span
        class="flex justify-start text-sm items-end duration-300 ease-in-out"
        >{{ buttonName }}</span
      >
    </button>
  </NuxtLink>
</template>

<script setup lang="ts">
defineProps({
  setColor: {
    type: String,
    required: false,
    default: "",
  },
  buttonName: {
    type: String,
    required: false,
    default: "",
  },
  rountingLink: {
    type: String,
    required: false,
    default: "",
  },
});
</script>

<style scoped></style>
