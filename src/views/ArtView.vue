<template>
  <h2 class="text-2xl md:text-3xl">{{ $route.params.id }}</h2>
  <p class="py-4 max-w-3xl">
    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
    tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
    quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
    consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse
    cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
    non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
  </p>
  <ul class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
    <li v-for="index in 10" :key="index">
      <img class="max-w-sm mx-auto" :src="require(`../assets/` + image + '')" />
      <h3 class="text-2xl text-center">Titel</h3>
    </li>
  </ul>
</template>

<script>
export default {
  data() {
    return {
      image: "logo.png",
    };
  },
};
</script>

<style></style>
