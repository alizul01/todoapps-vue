<template>
  <div class="container">
    <Header />
    <InputBox class="mt-4" />
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import InputBox from "@/components/InputBox.vue";
import { ref, onMounted, computed, watch } from "vue";
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
  components: { Header, InputBox },
};
</script>
