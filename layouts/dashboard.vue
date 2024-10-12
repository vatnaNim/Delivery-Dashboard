<template>
  <div class="flex h-full w-full bg-blue-100">
    <div class="w-[250px] h-screen bg-white fixed">
      <Sidebar />
    </div>

    <div
      class="ml-[250px] flex-1 h-full flex flex-col gap-2 box-border px-8 py-4"
    >
      <div class="w-full">
        <Header />
      </div>
      <main class="w-full overflow-hidden rounded-2xl">
        <slot />
      </main>
    </div>
  </div>
</template>

<script setup lang="ts"></script>

<style scoped>
::-webkit-scrollbar {
  display: none;
}
</style>
