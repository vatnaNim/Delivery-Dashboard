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
              d="M280-40q-33 0-56.5-23.5T200-120v-720q0-33 23.5-56.5T280-920h400q33 0 56.5 23.5T760-840v720q0 33-23.5 56.5T680-40H280Zm0-120v40h400v-40H280Zm0-80h400v-480H280v480Zm0-560h400v-40H280v40Zm0 0v-40 40Zm0 640v40-40Z"
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
