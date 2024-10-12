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
      <div class="m-auto">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 -960 960 960"
          fill="currentColor"
          class="w-6 h-6"
        >
          <path
            d="M240-160q-50 0-85-35t-35-85H40v-440q0-33 23.5-56.5T120-800h560v160h120l120 160v200h-80q0 50-35 85t-85 35q-50 0-85-35t-35-85H360q0 50-35 85t-85 35Zm0-80q17 0 28.5-11.5T280-280q0-17-11.5-28.5T240-320q-17 0-28.5 11.5T200-280q0 17 11.5 28.5T240-240ZM120-360h32q17-18 39-29t49-11q27 0 49 11t39 29h272v-360H120v360Zm600 120q17 0 28.5-11.5T760-280q0-17-11.5-28.5T720-320q-17 0-28.5 11.5T680-280q0 17 11.5 28.5T720-240Zm-40-200h170l-90-120h-80v120ZM360-540Z"
          />
        </svg>
      </div>
      <span
        class="flex justify-start text-sm items-end duration-300 ease-in-out"
      >
        {{ buttonName }}
      </span>
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
