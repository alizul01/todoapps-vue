<script setup>
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
import { ChevronDownIcon } from "@heroicons/vue/solid";
</script>

<template>
  <div class="relative mx-8">
    <Menu>
      <MenuButton>
        <i
          class="
            fa-solid fa-list
            absolute
            top-0
            left-0
            m-3
            text-2xl text-teal-600
          "
        >
        </i>
      </MenuButton>
      <MenuItems
        class="
          absolute
          mt-2
          w-56
          origin-top-right
          divide-y divide-gray-100
          rounded-md
          bg-white
          shadow-lg
          ring-1 ring-black ring-opacity-5
          focus:outline-none
        "
      >
        <div class="px-1 py-1">
          <MenuItem v-slot="{ active }" :key="tag.id" v-for="tag in tags">
            <button
              :class="[
                active ? `${tag.color} text-gray-900` : 'text-gray-900',
                'group flex w-full items-center rounded-md px-2 py-2 text-sm',
              ]"
            >
              {{ tag.name }}
            </button>
          </MenuItem>
        </div>
      </MenuItems>
    </Menu>
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
      tags: [
        {
          id: 1,
          name: "Productivity",
          color: "bg-teal-200",
        },
        {
          id: 2,
          name: "Personal",
          color: "bg-blue-200",
        },
        {
          id: 3,
          name: "Work",
          color: "bg-orange-200",
        },
        {
          id: 4,
          name: "Other",
          color: "bg-slate-200",
        },
      ],
    };
  },
  components: { ButtonBlockVue },
};
</script>
<style>
</style>