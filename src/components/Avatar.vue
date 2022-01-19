<template>
  <div class="avatar">
    <img src="link" alt="user avatar" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    link: String,
  },
})
export default class Avatar extends Vue {
  link: string;
}
</script>

<style scoped>
img {
}
</style>
