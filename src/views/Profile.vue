<template>
  <div class="profile">
    <p class="heading">Profile</p>
    <div class="userinfo">
      <img v-bind:src="profile?.avatar" alt="user avatar" />
      <p class="name">{{ profile.first_name }} {{ profile?.last_name }}</p>
      <p class="b-day">{{ profile?.date_of_birth }}</p>
      <p class="employment">
        {{ profile.employment?.title }} - {{ profile.employment?.key_skill }}
      </p>
      <p class="address">
        {{ profile.address?.city }}, {{ profile.address?.state }},
        {{ profile.address?.country }}
      </p>
    </div>
    <p class="heading">Your beer:</p>
    <div class="beer">
      <ul>
        <li>Brand: {{ beer.brand }}</li>
        <li>Name: {{ beer.name }}</li>
        <li>Style: {{ beer.style }}</li>
        <li>Hop: {{ beer.hop }}</li>
        <li>Yeast: {{ beer.yeast }}</li>
        <li>Malts: {{ beer.malts }}</li>
        <li>Bitterness: {{ beer.ibu }}</li>
        <li>Alcohol: {{ beer.alcohol }}</li>
        <li>Sugar: {{ beer.blg }}</li>
      </ul>
    </div>
    <button @click="getRandomBeer()">Get new beer</button>
  </div>
</template>

<script>
import { Options, Vue } from "vue-class-component";

@Options({
  data() {
    return { beer: this.getRandomBeer(), profile: this.getRandomProfile() };
  },
  components: {},
  methods: {
    async getRandomBeer() {
      try {
        await fetch("https://random-data-api.com/api/beer/random_beer").then(
          (req) => req.json().then((res) => (this.beer = res))
        );
      } catch (e) {
        console.log(e);
      }
    },
    async getRandomProfile() {
      try {
        await fetch("https://random-data-api.com/api/users/random_user").then(
          (req) => req.json().then((res) => (this.profile = res))
        );
      } catch (e) {
        console.log(e);
      }
    },
  },
})
export default class Profile extends Vue {}
</script>

<style scoped>
.heading {
  margin: 15px auto 0;
}

.userinfo {
  font-weight: normal;
  font-size: 0.8em;
}

.userinfo img {
  margin: 5px auto 0;
  width: 150px;
  height: 150px;
}

.userinfo p {
  color: #549b83;
}

.beer {
  margin: 10px auto;
}

ul {
  text-align: center;
  list-style: none;
  display: block;
  font-size: 0.8em;
  margin: 15px auto;
  color: #549b83;
}

li {
  margin: 5px auto;
}
</style>
