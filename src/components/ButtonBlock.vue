<template>
  <div>
    <button
      v-on:click="showData"
      :class="{
        'bg-teal-500 text-white hover:bg-teal-600 focus:ring focus:ring-teal-200':
          this.isPrimary,
        'border-teal-500 text-gray-700 hover:bg-teal-200': !this.isPrimary,
      }"
      class="p-4 rounded-lg transition-all duration-300"
    >
      {{ text }}
    </button>
  </div>
</template>
<script>
export default {
  name: "ButtonBlock",
  props: {
    text: {
      type: String,
      default: "Click me",
    },
    isPrimary: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    showData() {
      this.$emit("showMsg", 23);
    },
  },
};
</script>
<style>
</style>