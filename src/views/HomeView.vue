<template>
  <section
    class="border-2 max-h-96 border-gray-500 overflow-hidden box-sizing mb-8"
  >
    <img src="@\assets\hero.png" />
  </section>
  <section class="box-sizing">
    <ul class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8">
      <li v-for="(section, index) in artData" :key="section.name + index">
        <ArtLink
          :folder="section.name"
          :title="section.displayName"
          :image="section.children[0].name"
        />
      </li>
    </ul>
  </section>
</template>

<script>
import ArtLink from "@/components/ArtLink.vue";
import ArtJson from "../art.json";
export default {
  name: "HomeView",
  components: { ArtLink },
  data() {
    return {
      artData: [],
      titles: ["hello", "is", "it", "me", "you're", "looking", "for?"],
    };
  },

  mounted() {
    this.artData = ArtJson;
  },
};
</script>
