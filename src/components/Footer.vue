<template>
  <footer class="py-4">
    <!-- Top Features Section -->
    <div class="max-w-full px-4 lg:px-2 flex flex-row justify-center items-center lg:flex-row text-center bg-gray-100 py-4 lg:py-12 gap-6 lg:gap-12">
  <div class="space-y-2">
    <h4 class="text-[16px] lg:text-[20px] leading-tight lg:leading-snug font-semibold text-black">
      Free Delivery
    </h4>
    <p class="text-xs lg:text-sm text-black">
      On orders of Rs. 2999 or more
    </p>
  </div>
  <div class="space-y-2">
    <h4 class="text-[16px] lg:text-[20px] leading-tight lg:leading-snug font-semibold text-black">
      Shop with Confidence
    </h4>
    <p class="text-xs lg:text-sm text-black">
      With our 2-year guarantee
    </p>
  </div>
  <div class="space-y-2">
    <h4 class="text-[16px] lg:text-[20px] leading-tight lg:leading-snug font-semibold text-black">
      Love-it Guarantee
    </h4>
    <p class="text-xs lg:text-sm text-black">
      Available on all products
    </p>
  </div>
</div>


    <!-- Navigation Links Section -->
    <div class="max-w-7xl lg:mx-48 mt-12 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-8 text-center">
      <!-- Advisor Information -->
      <div>
        <h4 class="text-lg font-semibold text-gray-800 mb-4">Advisor Information</h4>
        <ul class="space-y-2 text-gray-600">
          <li><router-link to="#" class="hover:text-gray-800">Business Opportunity</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Find an Advisor</router-link></li>
        </ul>
      </div>

      <!-- About Us -->
      <div>
        <h4 class="text-lg font-semibold text-gray-800 mb-4">About Us</h4>
        <ul class="space-y-2 text-gray-600">
          <li><router-link to="#" class="hover:text-gray-800">Our Story</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Wellness</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Beauty</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Kitchen</router-link></li>
        </ul>
      </div>

      <!-- Social Links -->
      <div>
        <h4 class="text-lg font-semibold text-gray-800 mb-4">Social</h4>
        <ul class="space-y-2 text-gray-600">
          <li><router-link to="#" class="hover:text-gray-800">Facebook</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Instagram</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">YouTube</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">LinkedIn</router-link></li>
        </ul>
      </div>

      <!-- Customer Services -->
      <div>
        <h4 class="text-lg font-semibold text-gray-800 mb-4">Customer Services</h4>
        <ul class="space-y-2 text-gray-600">
          <li><router-link to="#" class="hover:text-gray-800">Terms & Conditions</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">FAQs</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Privacy Policy</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Policy & Compliance</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Cancellation & Return Policy</router-link></li>
          <li><router-link to="#" class="hover:text-gray-800">Contact Us</router-link></li>
        </ul>
      </div>
    </div>

    <!-- Footer Bottom Section -->
    <div class="border-t border-gray-500 mt-12 pt-6">
      <div class="text-center text-sm text-gray-600">
        <span class="text-gray-800">© 2024 All rights reserved. Modiway Ltd.</span>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style>
/* Add custom styles if needed */
</style>
