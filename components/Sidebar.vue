<template>
  <div
    class="w-full h-full overflow-y-auto shadow-xl border-blue-300 border-r-2 flex flex-col justify-start items-start"
  >
    <span
      class="w-full flex justify-center items-center py-4 px-2 sticky z-10 top-0 bg-white"
    >
      <img class="w-22 h-12" :src="mainLogo" alt="scr Logo" />
      <span class="text-center">
        <h1 class="text-xl font-bold text-blue-800">Robertson</h1>
        <p class="text-xs text-black">Success isn't given. It's earned</p>
      </span>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 -960 960 960"
        class="w-12 h-12 text-blue-800"
        fill="currentColor"
      >
        <path
          d="M440-240 200-480l240-240 56 56-183 184 183 184-56 56Zm264 0L464-480l240-240 56 56-183 184 183 184-56 56Z"
        />
      </svg>
    </span>

    <ul class="w-full my-4 flex flex-col gap-0.5 pr-0.5">
      <li>
        <UiActiveButtonDashboard
          buttonName="Dashboard"
          rountingLink="/"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonOrderImage
          buttonName="Order Image"
          rountingLink="/orderImage"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonPickupCenter
          buttonName="Pickup Center"
          rountingLink="/pickupCenter"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonPackageTrails
          buttonName="Package Trails"
          rountingLink="/packageTrails"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonFleetManagement
          buttonName="Fleet Management"
          rountingLink="/fleetManagement"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonCompletedDeliveries
          buttonName="Completed Deliveries"
          rountingLink="/completedDeliveries"
          setColor="text-blue-900 fill-blue-900 "
        />
      </li>
    </ul>

    <span
      class="w-full shadow-md shadow-gray-400 text-start px-4 text-base font-bold text-blue-900 border-b-2"
      >BILLNG AND PAYMENT</span
    >
    <ul class="w-full my-2 flex flex-col gap-0.5 pr-0.5">
      <li>
        <UiActiveButtonDriverTransaction
          buttonName="Driver Transaction"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonMerchantTransaction
          buttonName="Merchant Transaction"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonSaleTransaction
          buttonName="Sale Transaction"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonMerchantBalance
          buttonName="Merchant Balance"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
    </ul>

    <span
      class="w-full shadow-md shadow-gray-400 text-start px-4 text-base font-bold text-blue-900 border-b-2"
      >PARTNER MANAGEMENT</span
    >

    <ul class="w-full my-2 flex flex-col gap-0.5 pr-0.5">
      <li>
        <UiActiveButtonDriverManagement
          buttonName="Driver Management"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonMerchantManagement
          buttonName="Merchant Management"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonSaleManagement
          buttonName="Sale Management"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
    </ul>

    <span
      class="w-full shadow-md shadow-gray-400 text-start px-4 text-base font-bold text-blue-900 border-b-2"
      >REPORT CENTER</span
    >
    <ul class="w-full my-2 flex flex-col gap-0.5 pr-0.5">
      <li>
        <UiActiveButtonReportCenter
          buttonName="Report Center"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
    </ul>

    <span
      class="w-full shadow-md shadow-gray-400 text-start px-4 text-base font-bold text-blue-900 border-b-2"
      >SETTING MANAGEMENT</span
    >
    <ul class="w-full my-2 flex flex-col gap-0.5 pr-0.5">
      <li>
        <UiActiveButtonCompanyProfile
          buttonName="Company Profile"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonMobileSetting
          buttonName="Mobile Setting"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonGeneralSetting
          buttonName="General Setting"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <LazyUiActiveButtonUsersManagement
          buttonName="User Management"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
      <li>
        <UiActiveButtonLogOut
          buttonName="Log Out"
          rountingLink="/"
          setColor="text-blue-900 hover:fill-white fill-blue-900 "
        />
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { mainLogo } from "~/static/imagesHandle";
import iconDashBorad from "~/public/icons/dashBoard.svg";

const sideBarData = [
  {
    scr: iconDashBorad,
    dbName: "Dashboard",
  },
];
</script>

<style scoped></style>
