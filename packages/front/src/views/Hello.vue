<template>
  <div class="hello">
    <MyButton />
  </div>
</template>

<script>
// @ is an alias to /src
import MyButton from "@/components/MyButton.vue";

export default {
  name: "hello",
  components: {
    MyButton
  }
};
</script>
