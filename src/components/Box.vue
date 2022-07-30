<template>
  <div
    class="border relative border-teal-700 p-4 rounded-lg flex justify-between"
  >
    <div
      class="bg-teal-300 w-24 text-center absolute rounded-lg -top-3.5 left-8"
    >
      Tags
    </div>
    <div class="mr-4 p-2 rounded-lg">{{ date }}</div>
    <div class="p-2 flex-1">{{ text }}</div>
    <div class="ml-4 w-20 flex flex-row">
      <button
        class="border text-center bg-green-400 rounded-lg w-full p-2 mr-2"
      >
        <i class="fa-solid fa-check text-white"></i>
      </button>
      <button class="border text-center bg-red-400 rounded-lg w-full p-2">
        <i class="fa-solid fa-times text-white"></i>
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: "Box",
  props: {
    date: {
      type: String,
      default: `${new Date().getDate()}/${
        new Date().getMonth() + 1
      }/${new Date().getFullYear()}`,
    },
    text: {
      type: String,
      default: "Click me",
    },
  },
};
</script>
<style>
</style>