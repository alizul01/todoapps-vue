<template>
  <div class="relative mx-8">
    <slot name="tags"></slot>
    <input
      type="text"
      v-model="inputValue"
      class="
        w-full
        px-16
        py-3
        text-teal-600
        font-semibold
        text-lg
        border-2 border-teal-600
        rounded-lg
        hover:border-teal-600
        transition-all
        duration-300
        focus:outline-none focus:shadow-xl focus:ring-0
      "
    />
    <div @click="getInputValue">
      <slot name="button"></slot>
    </div>
  </div>
</template>
<script>
export default {
  name: "InputBox",
  methods: {
    getInputValue() {
      this.$emit("getInputValue", this.inputValue);
    },
  },
  data() {
    return {
      inputValue: "",
    };
  },
};
</script>
<style>
</style>