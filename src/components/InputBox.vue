<script setup>
import Tags from "./Tags.vue";
</script>

<template>
  <div class="relative mx-8">
    <slot></slot>
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
    <ButtonBlock
      @showMsg="getData($event)"
      class="absolute z-10 top-0 right-0"
      :isPrimary="true"
      text="Add"
    />
  </div>
</template>
<script>
import ButtonBlock from "@/components/ButtonBlock.vue";

export default {
  name: "InputBox",
  data() {
    return {
      inputValue: "",
    };
  },
  components: { ButtonBlock },
  methods: {
    printData(id) {
      this.$emit("getTagsData", getData());
    },
  },
};
</script>
<style>
</style>