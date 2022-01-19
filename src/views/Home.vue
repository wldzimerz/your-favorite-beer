<template>
  <div class="home">
    <img alt="Beer app logo" src="../assets/beer-logo.png" />
    <Greetings
      msg1="Welcome!"
      msg2="This app will determine the type of your favorite beer."
      msg3="Also you can use it if you can't choose a drink at the bar!"
    />
    <router-link to="/profile">
      <button>Try it!</button>
    </router-link>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import Greetings from "@/components/Greetings.vue";

@Options({
  components: {
    Greetings,
  },
})
export default class Home extends Vue {}
</script>

<style scoped>
.home img {
  margin: 10px auto 0;
  width: 50%;
  height: 50%;
}
@media screen and (min-width: 320px) {
  .home img {
    width: 60%;
    height: 60%;
  }
}
@media screen and (min-width: 768px) {
  .home img {
    width: 35%;
    height: 35%;
  }
}
</style>
