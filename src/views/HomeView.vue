<template>
  <div class="container">
    <Header />
    <InputBox @getInputValue="getData($event)" class="mt-4">
      <template v-slot:tags>
        <Tags @showTags="pushCategory($event)" class="absolute z-10" />
      </template>

      <template v-slot:button>
        <ButtonBlock
          class="absolute z-10 top-0 right-0"
          :isPrimary="true"
          text="Add"
          @click="addData"
        />
      </template>
    </InputBox>
    <div id="todo" class="mx-8 mt-24">
      <Box
        v-for="(item, index) in ToDoList.uncompleted"
        :key="index"
        :tags="item.tags"
        :isCompleted="item.isCompleted"
        :text="item"
        class="mt-4"
      />
    </div>

    <div id="done"></div>
  </div>
</template>

<script>
/**
 * TODO: FIX CATEGORY FILTERING
 */
import Header from "@/components/Header.vue";
import InputBox from "@/components/InputBox.vue";
import Box from "@/components/Box.vue";
import Tags from "@/components/Tags.vue";
import ButtonBlock from "@/components/ButtonBlock.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { Header, InputBox, Box, Tags, ButtonBlock },
  methods: {
    pushCategory(data) {
      if (this.inputCategory.find((item) => item === data)) {
        // remove item
        this.inputCategory = this.inputCategory.filter((item) => item !== data);
      } else {
        // add item
        this.inputCategory.push(data);
      }

      console.log(this.inputCategory);
    },
    getData(data) {
      this.inputValue = data;
      this.pushToDo();
    },
    getTags(data) {
      console.log(data);
    },
    pushToDo() {
      const value = this.inputValue;
      const tagsCategory = this.inputCategory;
      const newToDo = {
        id: +new Date(),
        tags: tagsCategory,
        text: value,
        completed: false,
      };

      this.ToDoList.uncompleted.push(newToDo);
      this.inputValue = "";
    },
    addData() {
      console.log(this.inputCategory);
    },
  },
  data() {
    return {
      inputValue: "",
      inputCategory: [],
      ToDoList: {
        uncompleted: [],
        completed: [],
      },
    };
  },
};
</script>
