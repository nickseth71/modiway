<template>
  <div class="flex flex-col px-4 py-3">
    <!-- Header Section -->
    <div class="flex justify-between items-center py-3 px-4 sm:px-6 lg:px-8">
      <!-- Left Side (Menu Button) -->
      <div class="flex items-center gap-4 sm:hidden">
        <!-- Menu Icon for Mobile Screens -->
        <button
          @click="isMenuOpen = !isMenuOpen"
          class="block p-2 rounded focus:outline-none"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16m-7 6h7"
            />
          </svg>
        </button>
      </div>

      <!-- Logo Section - Centered -->
      <div class="flex justify-center items-center flex-grow">
        <img
          :src="Logo"
          alt="ModiwayLogo"
          class="w-[150px] h-[30px] sm:w-[180px] sm:h-[36px] md:w-[200px] lg:w-[220px]"
        />
      </div>

      <!-- Right Side (Icons) -->
      <div class="flex gap-4 sm:gap-6 items-center">
        <!-- Search Icon -->
        <div class="flex items-center gap-2 lg:pr-4 ">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="cursor-pointer w-5 h-5 sm:w-6 sm:h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z"
            />
          </svg>
        </div>

        <!-- Profile Icon -->
        <div class="flex items-center gap-2 lg:pr-4 ">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.5"
            stroke="currentColor"
            class="cursor-pointer w-5 h-5 sm:w-6 sm:h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M15.75 6a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0ZM4.501 20.118a7.5 7.5 0 0 1 14.998 0A17.933 17.933 0 0 1 12 21.75c-2.676 0-5.216-.584-7.499-1.632Z"
            />
          </svg>
        </div>

        <!-- Cart Icon -->
        <div class="flex items-center gap-2">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            fill="none"
            viewBox="0 0 24 24"
            stroke-width="1.3"
            stroke="currentColor"
            class="cursor-pointer w-5 h-5 sm:w-6 sm:h-6"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M2.25 3h1.386c.51 0 .955.343 1.087.835l.383 1.437M7.5 14.25a3 3 0 0 0-3 3h15.75m-12.75-3h11.218c1.121-2.3 2.1-4.684 2.924-7.138a60.114 60.114 0 0 0-16.536-1.84M7.5 14.25 5.106 5.272M6 20.25a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Zm12.75 0a.75.75 0 1 1-1.5 0 .75.75 0 0 1 1.5 0Z"
            />
          </svg>
        </div>
      </div>
    </div>

    <!-- Navigation Links -->
    <nav>
  <ul
    :class="[isMenuOpen ? 'block' : 'hidden', 'sm:flex sm:flex-col md:flex-row justify-center text-sm md:text-base space-y-2 md:space-y-0 md:space-x-6']"
    class="space-y-2 md:space-y-0"
  >
    <li>
      <router-link
        to="/ourstory"
        class="cursor-pointer hover:text-gray-600 font-medium text-[15px]"
      >
        Our Story
      </router-link>
    </li>
    <li>
      <router-link
        to="/products"
        class="cursor-pointer hover:text-gray-600 font-medium text-[15px]"
      >
        Products
      </router-link>
    </li>
    <li>
      <router-link
        to="/business-opportunity"
        class="cursor-pointer hover:text-gray-600 font-medium text-[15px]"
      >
        Business Opportunity
      </router-link>
    </li>
    <li>
      <router-link
        to="/wellness-test"
        class="cursor-pointer hover:text-gray-600 font-medium text-[15px]"
      >
        Wellness Test
      </router-link>
    </li>
  </ul>
</nav>

  </div>
</template>

<script setup>
import Logo from "@/assets/ModiwayLogo.png";
import { ref } from "vue";

// State for toggling the menu
const isMenuOpen = ref(false);
</script>
