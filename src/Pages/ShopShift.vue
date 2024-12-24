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
            class="w-12 h-12 sm:w-14 sm:h-14 lg:w-16 lg:h-16 flex items-center justify-center bg-white text-black rounded-full shadow-lg hover:bg-gray-200 transition-transform duration-200"
            :aria-label="isPlaying ? 'Pause Video' : 'Play Video'"
          >
            <i
              :class="
                isPlaying
                  ? 'fas fa-pause text-lg sm:text-xl lg:text-2xl'
                  : 'fas fa-play text-lg sm:text-xl lg:text-2xl'
              "
            ></i>
          </button>
        </div>
      </div>
    </section>

    <!-- Welcome Section -->
    <section class="px-6 lg:px-20 py-5 lg:py-8">
      <div
        class="text-center flex max-w-[820px] mx-auto leading-5 lg:leading-[52px] text-[20px] lg:text-[36px] text-[#000000D9]"
      >
        Join us for a
        <h2 class="text-[24px] lg:text-[72px] font-medium lg:pl-4">
          90 Day Challenge
        </h2>
      </div>
      <div
        class="text-center text-[16px] font-normal lg:text-[20px] mx-auto max-w-[820px] leading-normal lg:leading-relaxed py-5"
      >
      Join us for a transformative journey towards balanced wellness, weight loss, and weight management,The Science of ShapeShifting.
      </div>
    </section>

    <!-- Individual Image Sections -->

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
      {
        type: "video",
        src: "https://cdn.pixabay.com/video/2022/02/24/108803-681686665_large.mp4",
      },
    ]);

    const imageItems = ref([
      {
        src: "path-to-image1",
        alt: "Image Alt Text 1",
        title: "Image Title 1",
        heading: "Heading 1",
        description: "Description 1",
      },
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
        currentIndex.value < mediaItems.value.length - 1
          ? currentIndex.value + 1
          : 0;
    };

    return {
      mediaItems,
      imageItems,
      currentIndex,
      isPlaying,
      togglePlayPause,
      nextSlide,
    };
  },
};
</script>
