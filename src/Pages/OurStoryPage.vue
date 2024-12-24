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
            :autoplay="isPlaying"
            playsinline
            class="block w-full h-full object-cover"
            ref="video"
            @play="isPlaying = true"
            @pause="isPlaying = false"
            @ended="nextSlide"
          />
          <!-- <img
            v-else
            :src="media.src"
            alt="Media item"
            class="block w-full h-full object-cover"
          /> -->
        </div>

        <!-- Video Control Buttons (Play/Pause) -->
        <div
          v-if="mediaItems[currentIndex].type === 'video' && !isPlaying"
          class="absolute inset-0 flex items-center justify-center"
        >
          <button
            @click="togglePlayPause"
            class="w-16 h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg"
          >
            <i class="fas fa-play text-2xl"></i>
          </button>
        </div>
        
        <div
          v-if="mediaItems[currentIndex].type === 'video' && isPlaying"
          class="absolute inset-0 flex items-center justify-center"
        >
          <button
            @click="togglePlayPause"
            class="w-16 h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg"
          >
            <i class="fas fa-pause text-2xl"></i>
          </button>
        </div>

        <!-- Carousel Controls -->
        <!-- <button
          type="button"
          class="absolute top-0 left-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
          @click="prevSlide"
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
            <span class="sr-only">Previous</span>
          </span>
        </button> -->

        <!-- <button
          type="button"
          class="absolute top-0 right-0 z-30 flex items-center justify-center h-full px-4 cursor-pointer group focus:outline-none"
          @click="nextSlide"
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
            <span class="sr-only">Next</span>
          </span>
        </button> -->

        <!-- Carousel Indicator (Dots) -->
        <!-- <div class="absolute bottom-4 left-1/2 transform -translate-x-1/2 flex space-x-2">
          <span
            v-for="(media, index) in mediaItems"
            :key="index"
            @click="currentIndex = index"
            class="w-3 h-3 bg-white rounded-full cursor-pointer"
            :class="{
              'bg-opacity-50': currentIndex !== index,
              'bg-opacity-100': currentIndex === index
            }"
          ></span>
        </div> -->
      </div>
    </section>

    <!-- Welcome Section -->
    <section class="lg:px-20 px-2 lg:py-8 py-5">
      <h1 class="lg:text-[48px] text-center font-extralight">Think Life Differently</h1>
      <div class="text-center max-w-[820px] mx-auto font-extralight leading-[30px] text-[18px] lg:text-[24px] text-[#000000]">
        All our products are designed to make that happen, backed by technology, science, research, innovation, functionality and creativity
      </div>
      <!-- <h3 class="font-semibold text-center">-Samir K Modi</h3> -->
    </section>

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
            :autoplay="isPlaying"
            playsinline
            class="block w-full h-full object-cover"
            ref="video"
            @play="isPlaying = true"
            @pause="isPlaying = false"
            @ended="nextSlide"
          />
          <!-- <img
            v-else
            :src="media.src"
            alt="Media item"
            class="block w-full h-full object-cover"
          /> -->
        </div>

        <!-- Video Control Buttons (Play/Pause) -->
        <div
          v-if="mediaItems[currentIndex].type === 'video' && !isPlaying"
          class="absolute inset-0 flex items-center justify-center"
        >
          <button
            @click="togglePlayPause"
            class="w-16 h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg"
          >
            <i class="fas fa-play text-2xl"></i>
          </button>
        </div>
        
        <div
          v-if="mediaItems[currentIndex].type === 'video' && isPlaying"
          class="absolute inset-0 flex items-center justify-center"
        >
          <button
            @click="togglePlayPause"
            class="w-16 h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg"
          >
            <i class="fas fa-pause text-2xl"></i>
          </button>
        </div>

        
      </div>
    </section>

    <!-- Individual Image Sections -->
    <div>
      <section
        v-for="(image, index) in imageItems"
        :key="index"
        :class="[
          'relative px-2 py-10',
          index === 1 ? 'bg-gray-100' : 'bg-white',
        ]"
      >
        <div class="container mx-auto lg:px-12">
          <div
            :class="{
              'flex flex-col items-center lg:flex-row-reverse lg:gap-6':
                index % 2 === 0,
              'flex flex-col items-center lg:flex-row lg:gap-6':
                index % 2 !== 0,
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
                class="absolute inset-0 flex px-7 py-4 items-start justify-start text-white font-extralight text-2xl bg-black/10 rounded-md"
              >
                {{ image.title }}
              </h3>
            </div>
            <!-- Description -->
            <div class="flex-1">
              <div class="px-2 lg:px-20 lg:py-28">
                <h3 class="text-xl lg:text-2xl mb-2">{{ image.heading }}</h3>
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

    <!-- Second Section -->
    <section class="lg:px-20 px-2 lg:py-8 py-5 bg-gray-100">
      <div class="text-center max-w-[820px] mx-auto leading-[38px] text-[18px] lg:text-[30px] text-[#000000D9]">
        Modiway is a future-forward direct-selling company. It offers the
        world’s best-designed, science-backed solutions and business
        opportunities to enhance your potential and make your dreams come true.
      </div>
    </section>

    <!-- Business Opportunity Section -->
    <section>
  <div class="relative flex items-center justify-center lg:h-full sm:h-48">
    <img
      :src="businessOpportunity"
      alt="Business Opportunity"
      class="w-full h-full object-cover"
    />
    <div class="absolute inset-0 flex flex-col items-start justify-center bg-black/30 rounded-md p-4">
      <h3 class="text-xl sm:text-3xl md:text-4xl lg:text-[48px] text-white font-semibold ml-4 sm:ml-6 md:ml-12 text-left mb-4">
        Business Opportunity
      </h3>
      <router-link
        to="#"
        class="underline text-white hover:text-blue-500 text-left text-sm sm:text-base ml-4 sm:ml-6 md:ml-12"
      >
        Learn More &gt;
      </router-link>
    </div>
  </div>
</section>



    <!-- Articles and Resources Section -->
    <section class="lg:mx-20 py-4 lg:p-6">
      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div>
          <img :src="ArticleIMG" alt="Article IMG" class="w-full object-cover" />
        </div>
        <div>
          <img :src="ResourceIMG" alt="Resource IMG" class="w-full object-cover" />
        </div>
      </div>
    </section>

    <!-- Footer -->
    <Footer />
  </section>
</template>

<script>
import { ref } from "vue";
import Footer from "@/components/Footer.vue";
import Thinkwellness from "@/assets/Thinkwellness.png";
import ThinkKitchen from "@/assets/ThinkKitchen.png";
import ThinkBeauty from "@/assets/ThinkBeauti.png";
import BusinessOpportunity from "@/assets/businessOpportunity.png";
import ResourceIMG from "@/assets/resources.png";
import ArticleIMG from "@/assets/Articles.png";
import '@fortawesome/fontawesome-free/css/all.css';


export default {
  components: {
    Footer,
  },
  setup() {
    const mediaItems = ref([
      {
        type: "video",
        src: "https://videos.pexels.com/video-files/2544523/2544523-hd_1920_1080_24fps.mp4",
      },
      // {
      //   type: "video",
      //   src: "https://cdn.pixabay.com/video/2022/11/22/140111-774507949_large.mp4",
      // },
      // {
      //   type: "video",
      //   src: "https://cdn.pixabay.com/video/2024/06/25/218213_large.mp4",
      // },
    ]);

    const imageItems = ref([
      {
        src: Thinkwellness,
        alt: "Think Wellness",
        title: "Think Wellness",
        heading: "Heading Here",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus volutpat massa quis lacus sollicitudin.",
      },
      {
        src: ThinkKitchen,
        alt: "Think Kitchen",
        title: "Think Kitchen",
        heading: "Heading Here",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus volutpat massa quis lacus sollicitudin.",
      },
      {
        src: ThinkBeauty,
        alt: "Think Beauty",
        title: "Think Beauty",
        heading: "Heading Here",
        description:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus volutpat massa quis lacus sollicitudin.",
      },
    ]);

    const businessOpportunity = BusinessOpportunity;

    const currentIndex = ref(0);
    const isPlaying = ref(false);

    const prevSlide = () => {
      currentIndex.value =
        (currentIndex.value - 1 + mediaItems.value.length) %
        mediaItems.value.length;
    };

    const nextSlide = () => {
      currentIndex.value = (currentIndex.value + 1) % mediaItems.value.length;
    };

    const togglePlayPause = () => {
      isPlaying.value = !isPlaying.value;
      const videoElement = document.querySelector("video");
      if (isPlaying.value) {
        videoElement.play();
      } else {
        videoElement.pause();
      }
    };


    return {
      mediaItems,
      imageItems,
      currentIndex,
      isPlaying,
      prevSlide,
      nextSlide,
      togglePlayPause,
      businessOpportunity,
      ArticleIMG,
      ResourceIMG,
    };
  },
};
</script>

<style scoped>
/* Optional styles here */
</style>
