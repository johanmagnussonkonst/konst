<template>
  <section class="border-2 max-h-96 border-gray-500 overflow-hidden box-sizing">
    <img
      class="max-w-sm mx-auto"
      style="height: 500px"
      src="@\assets\logo.png"
    />
  </section>
  <section class="py-4 box-sizing">
    <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <li v-for="(title, index) in titles" :key="title + index">
        <ArtLink :title="title" image="logo.png" />
      </li>
    </ul>
  </section>
</template>

<script>
import ArtLink from "@/components/ArtLink.vue";
export default {
  name: "HomeView",
  components: { ArtLink },
  data() {
    return {
      titles: [
        "hello",
        "is",
        "it",
        "me",
        "you're",
        "looking",
        "for?",
        "hello",
        "is",
        "it",
        "me",
        "you're",
        "looking",
        "for?",
      ],
    };
  },
};
</script>

<style lang="scss" scoped></style>
