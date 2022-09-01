<template>
  <router-link :to="'/art/' + title">
    <div class="p-4 box-content bg-red-300 hover:bg-red-500 transition-all">
      <h3 class="capitalize text-3xl mb-4">{{ title }}</h3>
      <img class="max-w-sm mx-auto" :src="require(`../assets/` + image + '')" />
    </div>
  </router-link>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "",
    },
    image: {
      type: String,
      default: "logo.png",
    },
  },
};
</script>

<style></style>
