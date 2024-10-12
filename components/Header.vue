<template>
  <div class="w-full h-10 flex gap-2 items-center">
    <span
      class="h-full w-[75%] px-6 py-1 bg-white rounded-full text-base font-bold flex justify-start items-center text-black"
    >
      PICKUP CENTER
    </span>

    <div class="relative w-[15%] h-full">
      <button
        class="bg-white text-black rounded-full w-full h-full py-1 px-2 flex items-center justify-center"
        @click="toggleDropdown"
      >
        <div
          class="w-full h-full grid grid-cols-[30%_50%_20%] gap-0.5 items-center"
        >
          <div
            class="w-6 h-6 overflow-hidden rounded-full flex-shrink-0 m-auto"
          >
            <img
              class="w-full h-full object-cover"
              :src="language[selectedLanguage].pfNation"
              alt="Flag"
            />
          </div>

          <span class="text-sm font-bold flex justify-center items-center">{{
            language[selectedLanguage].nation
          }}</span>

          <div class="flex justify-center items-center">
            <svg
              v-if="!isDropdownOpen"
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 -960 960 960"
              fill="currentColor"
              class="w-8 h-6"
            >
              <path d="M480-360 280-560h400L480-360Z" />
            </svg>
            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 -960 960 960"
              fill="currentColor"
              class="w-8 h-6"
            >
              <path d="M400-280v-400l200 200-200 200Z" />
            </svg>
          </div>
        </div>
      </button>

      <transition name="fade">
        <ul
          v-if="isDropdownOpen"
          class="absolute z-10 mt-1 w-full bg-white border border-gray-300 rounded-md shadow-lg overflow-hidden text-black"
        >
          <li
            v-for="(lang, index) in language"
            :key="lang.id"
            @click="selectLanguage(index)"
            :class="{
              'bg-gray-200': selectedLanguage === index,
              'hover:bg-gray-100': selectedLanguage !== index,
            }"
            class="flex items-center px-4 py-2 cursor-pointer"
          >
            <div class="w-6 h-6 overflow-hidden rounded-full flex-shrink-0">
              <img
                class="w-full h-full object-cover"
                :src="lang.pfNation"
                alt="Flag"
              />
            </div>
            <span class="ml-2 text-sm font-bold">{{ lang.nation }}</span>
          </li>
        </ul>
      </transition>
    </div>
    <button
      class="rounded-full w-[4%] h-full m-auto text-red-600 bg-white font-bold text-base"
    >
      20
    </button>

    <button
      class="bg-white rounded-full w-[15%] h-full flex items-center p-1 text-black"
    >
      <div class="w-8 h-8 rounded-full ml-1 overflow-hidden flex-shrink-0">
        <img
          class="w-full h-full object-cover"
          :src="currentUser?.userProfile"
          alt="User Profile"
        />
      </div>
      <span class="ml-2 flex justify-start items-center text-base font-bold">{{
        currentUser?.userName
      }}</span>
    </button>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import { englishFlag, cambodiaFlag, user1, user2 } from "~/static/imagesHandle";

interface iLanguage {
  id: number;
  nation: string;
  pfNation: string;
}
const language: iLanguage[] = [
  {
    id: 1,
    nation: "English",
    pfNation: englishFlag,
  },
  {
    id: 2,
    nation: "Cambodia",
    pfNation: cambodiaFlag,
  },
];

interface iUser {
  usersId: number;
  userName: string;
  userProfile: string;
}
const users: iUser[] = [
  {
    usersId: 1,
    userName: "Pech Panha",
    userProfile: user1,
  },
  {
    usersId: 2,
    userName: "Nim Vatna",
    userProfile: user2,
  },
];

const currentUser = users.find((user) => user.usersId === 2);

const isDropdownOpen = ref(false);
const selectedLanguage = ref(0);

const toggleDropdown = () => {
  isDropdownOpen.value = !isDropdownOpen.value;
};

const selectLanguage = (index: number) => {
  selectedLanguage.value = index;
  isDropdownOpen.value = false;
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter,
.fade-leave-to {
  opacity: 0;
}
</style>
