<template>
  <div class="flex gap-0.5 flex-col">
    <label :for="labalId" class="font-bold text-xs">{{ labalName }}</label>
    <input
      :id="labalId"
      :type="typeOfInput"
      class="px-3 py-1 bg-white border border-gray-400 rounded-md text-md font-semibold focus:ring-2 focus:border-0 ring-blue-500"
      :value="customValue"
      :placeholder="placeHolder"
    />
  </div>
</template>

<script setup lang="ts">
defineProps({
  labalName: {
    type: String,
    required: true,
  },
  typeOfInput: {
    type: String,
    required: true,
  },
  placeHolder: {
    type: String,
    required: false,
    default: "",
  },
  customValue: {
    type: String,
    required: false,
    default: "",
  },
  labalId: {
    type: String,
    required: false,
    default: "",
  },
});
</script>

<style scoped></style>
