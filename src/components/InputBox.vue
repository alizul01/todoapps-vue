<template>
  <div class="relative mx-8">
    <i
      class="
        fa-solid fa-circle-plus
        absolute
        top-0
        left-0
        m-4
        text-2xl text-teal-600
      "
    ></i>
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
        border-2 border-teal-700
        rounded-lg
        hover:border-teal-600
        transition-all
        duration-300
      "
    />
    <ButtonBlockVue
      class="absolute z-10 top-0 right-0"
      :isPrimary="true"
      text="Add"
    />
  </div>
</template>
<script>
import ButtonBlockVue from "./ButtonBlock.vue";
export default {
  name: "InputBox",
  data() {
    return {
      inputValue: "",
    };
  },
  components: { ButtonBlockVue },
};
</script>
<style>
</style>