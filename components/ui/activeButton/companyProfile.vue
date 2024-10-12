<template>
  <NuxtLink :to="rountingLink">
    <button
      class="w-full flex justify-between items-center hover:bg-blue-900 hover:text-white py-1 px-4 rounded-r-full font-bold hover:shadow-md shadow-gray-400 transition-shadow"
      :class="setColor"
    >
      <div class="w-full grid grid-cols-[20%_80%] gap-2">
        <div class="m-auto">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 -960 960 960"
            fill="currentColor"
            class="w-6 h-6"
          >
            <path
              d="M120-120v-560h160v-160h400v320h160v400H520v-160h-80v160H120Zm80-80h80v-80h-80v80Zm0-160h80v-80h-80v80Zm0-160h80v-80h-80v80Zm160 160h80v-80h-80v80Zm0-160h80v-80h-80v80Zm0-160h80v-80h-80v80Zm160 320h80v-80h-80v80Zm0-160h80v-80h-80v80Zm0-160h80v-80h-80v80Zm160 480h80v-80h-80v80Zm0-160h80v-80h-80v80Z"
            />
          </svg>
        </div>
        <span
          class="flex justify-start text-sm items-end duration-300 ease-in-out"
          >{{ buttonName }}</span
        >
      </div>

      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 -960 960 960"
        fill="currentColor"
        class="w-6 h-6"
      >
        <path d="M504-480 320-664l56-56 240 240-240 240-56-56 184-184Z" />
      </svg>
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
