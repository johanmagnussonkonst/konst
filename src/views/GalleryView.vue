<template>
  <div class="bg-white mx-auto" v-if="showModal">
    <div class="mx-auto text-right text-4xl font-bold cursor-pointer">
      <span @click="closeModal"> ✕ </span>
    </div>
    <img
      class="mx-auto max-h-full max-w-full object-cover"
      :src="require(`../assets/art/` + folderName + activeImage.name + '')"
    />
  </div>
  <div v-else class="px-4">
    <h2 class="text-2xl md:text-3xl">{{ $route.params.id }}</h2>
    <p class="pt-2 pb-8 max-w-3xl">
      {{ description }}
    </p>
    <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <li
        class="flex flex-col justify-end"
        v-for="(image, index) in images"
        :key="index"
        @click="openModal(image)"
      >
        <img
          class="max-w-sm max-h-72 mx-auto"
          :src="require(`../assets/art/` + folderName + image.name + '')"
        />
        <h3 class="text-xl pt-2 text-center">{{ image.displayName }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
import ArtJson from "../art.json";

export default {
  data() {
    return {
      image: "logo.png",
      description: "",
      images: [],
      folderName: "",
      showModal: false,
      activeImage: "",
      oldPos: 0,
    };
  },

  created() {
    let found = false;
    ArtJson.forEach((section) => {
      if (section.displayName === this.$route.params.id) {
        this.folderName = section.name + "/";
        this.description = section.description;
        this.images = section.children;
        found = true;
        return;
      }
    });
    // Navigate to landing page if page not found
    if (!found) this.$router.push({ path: "/" });
  },

  mounted() {
    window.scrollTo(0, 0);
  },

  methods: {
    openModal(image) {
      this.showModal = true;
      this.activeImage = image;

      if (window.scrollY) {
        this.oldPos = window.scrollY;
        window.scrollTo(0, 0);
      }
    },
    closeModal() {
      this.showModal = false;

      window.scrollTo(0, this.oldPos);
    },
  },
};
</script>

<style></style>
