<template>
  <NuxtLink :to="rountingLink">
    <button
      class="w-full grid grid-cols-[20%_80%] gap-2 hover:bg-blue-900 hover:text-white py-1 px-4 rounded-r-full font-bold hover:shadow-md shadow-gray-400 transition-shadow"
      :class="setColor"
    >
      <div class="m-auto">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 -960 960 960"
          fill="currentColor"
          class="w-6 h-6"
        >
          <path
            d="M120-120v-80l80-80v160h-80Zm160 0v-240l80-80v320h-80Zm160 0v-320l80 81v239h-80Zm160 0v-239l80-80v319h-80Zm160 0v-400l80-80v480h-80ZM120-327v-113l280-280 160 160 280-280v113L560-447 400-607 120-327Z"
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
