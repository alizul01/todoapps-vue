<script setup>
import { Menu, MenuButton, MenuItem, MenuItems } from "@headlessui/vue";
import { ChevronDownIcon } from "@heroicons/vue/solid";
</script>
<template lang="">
    <div>
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
                    block
                    mt-8
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
                    <MenuItem @click="getTags(tag.id)" v-slot="{ active }" :key="tag.id" v-for="tag in tags">
                        <button @click="setChoosenTag(tag.id)"
                            :class="[active ? `${tag.color} text-gray-900` : 'text-gray-900',
                                'group flex w-full items-center rounded-md px-2 py-2 mt-2 text-sm', tag.choosen ? 'bg-gray-100' : '']"
                            >
                            {{ tag.name }}
                        </button>
                    </MenuItem>
                </div>
            </MenuItems>
        </Menu>
    </div>
</template>
<script>
export default {
  name: "Tags",
  data() {
    return {
      tags: [
        {
          id: 1,
          name: "Productivity",
          color: "bg-teal-200",
          choosen: false,
        },
        {
          id: 2,
          name: "Personal",
          color: "bg-blue-200",
          choosen: false,
        },
        {
          id: 3,
          name: "Work",
          color: "bg-orange-200",
          choosen: false,
        },
        {
          id: 4,
          name: "Other",
          color: "bg-slate-200",
          choosen: false,
        },
      ],
    };
  },
  methods: {
    getTags(id) {
      this.$emit("showTags", this.tags[id - 1].name);
    },
    setChoosenTag(id) {
      if (this.tags[id - 1].choosen) {
        this.tags[id - 1].choosen = false;
      } else {
        this.tags[id - 1].choosen = true;
      }
    },
  },
};
</script>
<style lang="">
</style>