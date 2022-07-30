<template>
  <div class="container">
    <Header />
    <InputBox class="mt-4">
      <Tags @showTags="getData($event)" class="absolute z-10"
    /></InputBox>
    <Box class="mt-24 mx-8" />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import InputBox from "@/components/InputBox.vue";
import { ref, onMounted, computed, watch } from "vue";
import Box from "@/components/Box.vue";
import Tags from "@/components/Tags.vue";
// @ is an alias to /src

const todos = ref([]);
const name = ref("");

const input_content = ref("");
const input_category = ref(null);

const todos_asc = computed(() =>
  todos.value.sort((a, b) => {
    return a.createdAt - b.createdAt;
  })
);

export default {
  name: "HomeView",
  components: { Header, InputBox, Box, Tags },
  methods: {
    printData() {
      console.log("printData");
    },
    getData(data) {
      console.log(data);
    },
  },
};
</script>
