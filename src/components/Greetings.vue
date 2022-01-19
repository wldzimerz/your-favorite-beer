<template>
  <div class="hello">
    <h1>{{ msg1 }}</h1>
    <p>{{ msg2 }}</p>
    <p>{{ msg3 }}</p>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    msg1: String,
    msg2: String,
    msg3: String,
  },
})
export default class Greetings extends Vue {
  msg1!: string;
  msg2!: string;
  msg3!: string;
}
</script>

<style scoped>
h1 {
  margin: 25px 0;
  font-size: 1em;
}

p {
  font-size: 0.7em;
  margin: 15px 0;
}
</style>
