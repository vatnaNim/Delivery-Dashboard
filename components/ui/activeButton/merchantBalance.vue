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
            d="M280-216q-50 0-85-35t-35-85v-360h80v360q0 17 11.5 28.5T280-296q17 0 28.5-11.5T320-336v-240q0-50 35-85t85-35q50 0 85 35t35 85v240q0 17 11.5 28.5T600-296q17 0 28.5-11.5T640-336v-280q0-50 35-85t85-35h47l-47-47 56-57 144 144-144 143-56-57 47-46h-47q-17 0-28.5 11.5T720-616v280q0 50-35 85t-85 35q-50 0-85-35t-35-85v-240q0-17-11.5-28.5T440-616q-17 0-28.5 11.5T400-576v240q0 50-35 85t-85 35ZM120-96q-33 0-56.5-23.5T40-176v-320h880v320q0 33-23.5 56.5T840-96H120Zm0-80h720v-240H120v240Zm720-240H120h720Z"
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
