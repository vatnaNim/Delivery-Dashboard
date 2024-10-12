<template>
  <div class="bg-white w-full h-full flex flex-col">
    <div class="w-full flex gap-3 items-center py-3 px-5">
      <button
        class="text-black border py-1.5 px-8 rounded-md text-sm font-semibold border-gray-300 shadow-sm hover:bg-gray-100"
      >
        New Order
      </button>
      <button
        class="text-black border py-1.5 px-8 rounded-md text-sm font-semibold border-gray-300 shadow-sm hover:bg-gray-100"
      >
        Quick Order
      </button>
      <UButtonGroup
        size="sm"
        orientation="horizontal"
        class="space-x-0 border border-gray-300"
      >
        <UButton
          label="Quick Order"
          color="black"
          class="py-1.5 px-8 text-sm font-semibold shadow-sm hover:bg-gray-100 border-r"
        />
        <UButton
          icon="fa6-solid:arrows-rotate"
          color="black"
          style="color: green; font-weight: bolder"
          class="py-1.5 px-2 text-sm font-semibold border-gray-300 shadow-sm hover:bg-gray-500 bg-white"
        />
      </UButtonGroup>

      <UButton
        icon="tabler:adjustments"
        color="black"
        style="color: blue"
        class="py-1.5 px-2 text-sm font-semibold border-gray-300 shadow-sm border bg-white hover:shadow-lg"
      />
    </div>

    <div class="w-full h-screen bg-gray-200 flex py-5 px-4 gap-1">
      <div class="w-1/2 h-full pr-0.5 border-r border-green-800">
        <div
          class="relative w-full h-full border border-orange-600 rounded-2xl p-2 flex justify-center items-center"
        >
          <transition name="fade" mode="out-in">
            <img
              v-bind:key="currentImage.scrId"
              class="w-full h-full object-cover rounded-lg"
              :src="currentImage.scr"
              alt="image_project"
            />
          </transition>
          <div class="w-full flex justify-between absolute">
            <button
              class="hover:text-orange-500 text-red-700 z-50"
              @click="prevImage"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-[70px] h-[200px]"
                viewBox="0 0 24 24"
              >
                <path
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2.5"
                  d="m14 7l-5 5m0 0l5 5"
                />
              </svg>
            </button>
            <button
              class="hover:text-orange-500 text-red-700 z-50"
              @click="nextImage"
            >
              <svg
                xmlns="http://www.w3.org/2000/svg"
                class="w-[70px] h-[200px]"
                viewBox="0 0 24 24"
              >
                <path
                  fill="none"
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="m10 17l5-5m0 0l-5-5"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>

      <form
        @submit.prevent="submitForm"
        class="w-[50%] h-full border border-orange-600 rounded-2xl px-4 py-2 text-black bg-white flex flex-col gap-2"
      >
        <h1 class="font-bold text-lg">DATA ENTRY</h1>
        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-name="MERCHANT"
            labal-id="001"
            custom-value="សុភមង្គលពិត_TURE HAPPINESS"
            type-of-input="text"
            class="w-2/4"
          />
          <ValueInput
            labal-name="ORDER NUMBER"
            labal-id="002"
            custom-value="HE009845445000000"
            type-of-input="text"
            class="w-2/4"
          />
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <div class="flex flex-col w-2/4 gap-0.5">
            <label for="people-select" class="font-bold text-xs"
              >DEFAULT DELIVERY TYPE</label
            >
            <select
              id="people-select"
              v-model="selected"
              class="w-full px-3 py-1.5 bg-white text-black border border-gray-400 rounded-md text-sm font-semibold focus:ring-2 focus:border-0 ring-blue-500 selection:bg-gray-300 selection:text-black"
            >
              <option value="">Nomal</option>

              <option
                v-for="person in deliveryType"
                :key="person.value"
                :value="person.value"
                class="font-medium"
              >
                {{ person.label }}
              </option>
            </select>
          </div>

          <ValueInput
            labal-name="PACKAGE COUNTS"
            labal-id="003"
            custom-value="10"
            type-of-input="text"
            class="w-2/4"
          />
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-name="ZONE*"
            type-of-input="text"
            class="w-2/4"
            labal-id="004"
          />
          <ValueInput
            labal-id="005"
            labal-name="RECEIVER PHONE*"
            type-of-input="text"
            class="w-2/4"
          />
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput labal-name="PRICE*" type-of-input="text" class="w-2/4" />
          <div class="flex flex-col w-2/4 gap-0.5">
            <label for="006" class="font-bold text-xs">COD*</label>
            <select
              id="006"
              v-model="selected"
              class="w-full px-3 py-1.5 bg-white text-black border border-gray-400 rounded-md text-sm font-semibold focus:ring-2 focus:border-0 ring-blue-500 selection:bg-gray-300 selection:text-black"
            >
              <option value="">Yes</option>

              <option
                v-for="person in codDb"
                :key="person.value"
                :value="person.value"
                class="font-medium"
              >
                {{ person.label }}
              </option>
            </select>
          </div>
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <div class="flex flex-col w-2/4 gap-0.5">
            <label for="007" class="font-bold text-xs">FEE PLAYER*</label>
            <select
              id="007"
              v-model="selected"
              class="w-full px-3 py-1.5 bg-white text-black border border-gray-400 rounded-md text-sm font-semibold focus:ring-2 focus:border-0 ring-blue-500 selection:bg-gray-300 selection:text-black"
            >
              <option value="" selected>Sender</option>

              <option
                v-for="person in FeePlayer"
                :key="person.value"
                :value="person.value"
                class="font-medium"
              >
                {{ person.label }}
              </option>
            </select>
          </div>
          <ValueInput
            labal-name="FEES"
            type-of-input="text"
            class="w-2/4"
            labal-id="008"
          />
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-name="RECEIVE ADDRESS"
            type-of-input="text"
            class="w-full"
          />
        </div>

        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-name="SIZE"
            type-of-input="text"
            class="w-2/4"
            labal-id="009"
          />
          <ValueInput
            labal-id="010"
            labal-name="AUTUAL KG"
            type-of-input="text"
            class="w-2/4"
          />
        </div>
        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-id="011"
            labal-name="BILLED KG"
            type-of-input="text"
            class="w-2/4"
          />
          <ValueInput
            labal-id="012"
            labal-name="BASE FEE"
            type-of-input="text"
            class="w-2/4"
          />
        </div>
        <div class="w-full flex justify-between items-start gap-4">
          <ValueInput
            labal-id="013"
            labal-name="ADDITIONAL FEES"
            type-of-input="text"
            class="w-2/4"
          />
          <ValueInput
            labal-name="TOTAL"
            type-of-input="text"
            class="w-2/4"
            labal-id="014"
          />
        </div>

        <div class="w-full h-full flex justify-between items-center">
          <button
            @click="submitForm"
            class="px-6 text-sm font-semibold py-1 bg-green-700 text-white rounded-full hover:bg-green-500 duration-300"
          >
            Save and Close
          </button>

          <span
            class="w-6 h-6 bg-orange-800 border border-green-800 flex justify-center items-center text-white p-5 rounded-full"
            >1</span
          >

          <button
            @click="submitForm"
            class="px-6 text-sm font-semibold py-1 bg-green-700 text-white rounded-full hover:bg-green-500 duration-300"
          >
            Save
          </button>
        </div>
      </form>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import { image1, image2, image3, image4 } from "@/static/imagesHandle";
import ValueInput from "~/components/ui/input/valueInput.vue";

interface iImagesHandler {
  scrId: number;
  scr: string;
}

const selected = ref("");
const deliveryType = [
  { value: 1, label: "Car" },
  { value: 2, label: "Bike" },
  { value: 3, label: "Boat" },
];

const codDb = [
  { value: 1, label: "No" },
  { value: 2, label: "Nomal" },
];

const FeePlayer = [{ value: 1, label: "Contact" }];

const imagesHandler: iImagesHandler[] = [
  { scrId: 1, scr: image1 },
  { scrId: 2, scr: image2 },
  { scrId: 3, scr: image3 },
  { scrId: 4, scr: image4 },
];

const currentIndex = ref(0);
const currentImage = ref(imagesHandler[currentIndex.value]);

const prevImage = () => {
  currentIndex.value =
    (currentIndex.value - 1 + imagesHandler.length) % imagesHandler.length;
  currentImage.value = imagesHandler[currentIndex.value];
};

const nextImage = () => {
  currentIndex.value = (currentIndex.value + 1) % imagesHandler.length;
  currentImage.value = imagesHandler[currentIndex.value];
};

const merchant = ref("សុភមង្គលពិត_TURE HAPPINESS");
const orderNumber = ref("HE009845445000000");
const packageCounts = ref("10");
const zone = ref("");
const receiverPhone = ref("");
const price = ref("");
const fees = ref("");
const receiveAddress = ref("");
const size = ref("");
const actualKg = ref("");
const billedKg = ref("");
const baseFee = ref("");
const additionalFees = ref("");
const total = ref("");

const submitForm = () => {
  console.log({
    merchant: merchant.value,
    orderNumber: orderNumber.value,
    packageCounts: packageCounts.value,
    zone: zone.value,
    receiverPhone: receiverPhone.value,
    price: price.value,
    fees: fees.value,
    receiveAddress: receiveAddress.value,
    size: size.value,
    actualKg: actualKg.value,
    billedKg: billedKg.value,
    baseFee: baseFee.value,
    additionalFees: additionalFees.value,
    total: total.value,
    selectedDeliveryType: selected.value,
  });
};

definePageMeta({ layout: "dashboard" });
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
