<template>
    <section>
      <!-- Video Carousel Section -->
      <section id="video-carousel" class="relative w-full h-screen">
        <div class="relative w-full h-full overflow-hidden">
          <!-- Video Items -->
          <div
            v-for="(media, index) in mediaItems"
            :key="index"
            class="absolute inset-0 w-full h-full duration-700 ease-in-out"
            v-show="index === currentIndex"
          >
            <video
              v-if="media.type === 'video'"
              :src="media.src"
              muted
              autoplay
              playsinline
              class="block w-full h-full object-cover"
              ref="video"
              @play="isPlaying = true"
              @pause="isPlaying = false"
              @ended="nextSlide"
            />
          </div>
  
          <!-- Video Control Button (Play/Pause) -->
          <div
            v-if="mediaItems[currentIndex].type === 'video'"
            class="absolute inset-0 flex items-center justify-center"
          >
            <button
              @click="togglePlayPause"
              class="w-16 h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg"
              :aria-label="isPlaying ? 'Pause Video' : 'Play Video'"
            >
              <i :class="isPlaying ? 'fas fa-pause text-2xl' : 'fas fa-play text-2xl'"></i>
            </button>
          </div>
  
          <!-- Carousel Controls -->
          <!-- <button
            type="button"
            class="absolute top-0 left-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
            @click="prevSlide"
            aria-label="Previous Slide"
          >
            <span
              class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-white/30 group-hover:bg-white/50 group-focus:ring-4 group-focus:ring-white"
            >
              <svg
                class="w-4 h-4 text-white"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 6 10"
              >
                <path
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M5 1 1 5l4 4"
                />
              </svg>
            </span>
          </button>
  
          <button
            type="button"
            class="absolute top-0 right-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
            @click="nextSlide"
            aria-label="Next Slide"
          >
            <span
              class="inline-flex items-center justify-center w-10 h-10 rounded-full bg-white/30 group-hover:bg-white/50 group-focus:ring-4 group-focus:ring-white"
            >
              <svg
                class="w-4 h-4 text-white"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 6 10"
              >
                <path
                  stroke="currentColor"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="m1 9 4-4-4-4"
                />
              </svg>
            </span>
          </button> -->
  
          <!-- Carousel Indicators (Dots) -->
          <!-- <div class="absolute hidden bottom-4 left-1/2 transform -translate-x-1/2 lg:flex space-x-2">
            <span
              v-for="(media, index) in mediaItems"
              :key="index"
              @click="currentIndex = index"
              class="w-3 h-3 bg-white rounded-full cursor-pointer"
              :class="{
                'bg-opacity-50': currentIndex !== index,
                'bg-opacity-100': currentIndex === index,
              }"
            ></span>
          </div> -->
        </div>
      </section>
  
      <!-- Welcome Section -->
      <section class="lg:px-20 px-[35px] lg:py-8 py-5">
        <div
          class="text-center max-w-[820px] mx-auto sm:leading-[20px] lg:leading-[38px] text-[16px] lg:text-[30px] text-[#000000D9]"
        >
          Welcome to a movement called the MODIWAY — a transformative journey to
          spread joy, make lives simpler, inspire positive change for body, mind,
          and soul, and build a better world.
        </div>
      </section>
  
      <!-- Individual Image Sections -->
      <div>
        <section
          v-for="(image, index) in imageItems"
          :key="index"
          class="relative py-10 bg-[#ffff]"
        >
          <div class="container mx-auto lg:px-12">
            <div
              :class="{
                'flex flex-col items-center lg:flex-row-reverse lg:gap-6': index % 2 === 0,
                'flex flex-col items-center lg:flex-row lg:gap-6': index % 2 !== 0,
              }"
            >
              <!-- Image with Title Overlay -->
              <div
                class="relative w-full lg:w-[500px] h-64 lg:h-[436px] mb-4 lg:mb-0 lg:mr-4 lg:ml-8"
              >
                <img
                  :src="image.src"
                  :alt="image.alt"
                  class="w-full h-full object-cover"
                />
                <h3
                  class="absolute inset-0 flex px-7 py-6 items-start justify-start text-white font-extralight text-lg lg:text-[48px] bg-black/15"
                >
                  {{ image.title }}
                </h3>
              </div>
              <!-- Description -->
              <div class="flex-1 justify-center items-start">
                <div class="px-[35.5px] lg:px-48 lg:py-28">
                  <h3 class="text-[26px] lg:text-2xl mb-2">{{ image.heading }}</h3>
                  <p class="text-[14px] lg:text-[20px] text-gray-700 mb-8">
                    {{ image.description }}
                  </p>
                  <router-link
                    to="#"
                    class="cursor-pointer underline hover:text-blue-500"
                  >
                    Shop Now &gt;
                  </router-link>
                </div>
              </div>
            </div>
          </div>
        </section>
      </div>
  
      <!-- Footer -->
      <Footer />
    </section>
  </template>
  
  <script>
  import { ref } from "vue";
  import Footer from "@/components/Footer.vue";
  
  export default {
    components: { Footer },
    setup() {
      const mediaItems = ref([
        { type: "video", src: "https://media.gettyimages.com/id/1192832836/video/silhouette-of-a-beautiful-yoga-woman-on-a-beach-she-is-performing-yoga-in-front-of-beautiful.mp4?s=mp4-640x640-gi&k=20&c=VfLb5DOZ8ZUH2inRB0YqM2ot5w-Y_VzcyAjnkf1_Kvg=" },
        // { type: "video", src: "https://cdn.pixabay.com/video/2022/11/22/140111-774507949_large.mp4" },
        // { type: "video", src: "https://cdn.pixabay.com/video/2024/06/25/218213_large.mp4" },
      ]);
  
      const imageItems = ref([
        {
          src: "path-to-image1",
          alt: "Image Alt Text 1",
          title: "Image Title 1",
          heading: "Heading 1",
          description: "Description 1",
        },
        // Add more image items here
      ]);
  
      const currentIndex = ref(0);
      const isPlaying = ref(false);
  
      const togglePlayPause = () => {
        isPlaying.value = !isPlaying.value;
        const video = document.querySelector("video");
        isPlaying.value ? video.play() : video.pause();
      };
  
      const nextSlide = () => {
        currentIndex.value =
          currentIndex.value < mediaItems.value.length - 1 ? currentIndex.value + 1 : 0;
      };
  
      const prevSlide = () => {
        currentIndex.value =
          currentIndex.value > 0 ? currentIndex.value - 1 : mediaItems.value.length - 1;
      };
  
      return {
        mediaItems,
        imageItems,
        currentIndex,
        isPlaying,
        togglePlayPause,
        nextSlide,
        prevSlide,
      };
    },
  };
  </script>
  