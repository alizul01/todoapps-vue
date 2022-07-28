<template>
  <div class="container">
    <Header />
    <InputBox />
    <ButtonBlock :isPrimary="true" text="Click me" />
  </div>
</template>

<script>
import ButtonBlock from "@/components/ButtonBlock.vue";
import Header from "@/components/Header.vue";
import InputBox from "@/components/InputBox.vue";
// @ is an alias to /src

export default {
  name: "HomeView",
  components: { ButtonBlock, Header, InputBox },
};
</script>
