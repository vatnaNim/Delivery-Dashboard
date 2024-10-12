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
            d="M360-200v-80h480v80H360Zm0-240v-80h480v80H360Zm0-240v-80h480v80H360ZM200-160q-33 0-56.5-23.5T120-240q0-33 23.5-56.5T200-320q33 0 56.5 23.5T280-240q0 33-23.5 56.5T200-160Zm0-240q-33 0-56.5-23.5T120-480q0-33 23.5-56.5T200-560q33 0 56.5 23.5T280-480q0 33-23.5 56.5T200-400Zm0-240q-33 0-56.5-23.5T120-720q0-33 23.5-56.5T200-800q33 0 56.5 23.5T280-720q0 33-23.5 56.5T200-640Z"
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
