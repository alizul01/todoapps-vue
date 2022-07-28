<template>
  <div class="relative">
    <i
      class="fa-solid fa-clone absolute top-0 left-0 m-4 text-2xl text-teal-600"
    ></i>
    <input
      type="text"
      v-model="inputValue"
      class="
        w-full
        px-16
        py-4
        text-teal-600
        font-semibold
        text-lg
        border-2 border-teal-700
        rounded-lg
        hover:border-teal-600
        transition-all
        duration-300
      "
    />
  </div>
</template>
<script>
export default {
  name: "InputBox",
  data() {
    return {
      inputValue: "",
    };
  },
};
</script>
<style>
</style>