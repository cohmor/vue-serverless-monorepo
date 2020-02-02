<template>
  <div class="hello">
    <button type="button" @click="onClick">call api</button>
    <p>{{ msg }}</p>
  </div>
</template>

<script lang="ts">
import axios from "axios";
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class MyButton extends Vue {
  msg: string = "click the button";

  async onClick(): Promise<void> {
    try {
      const { data } = await axios.get(`${process.env.VUE_APP_API_URL}/hello`);
      this.msg = data;
    } catch (error) {
      this.msg = error.message;
    }
  }
}
</script>

<style scoped lang="scss">
p {
  color: #42b983;
}
</style>
