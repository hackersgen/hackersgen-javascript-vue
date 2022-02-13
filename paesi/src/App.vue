<template>
  <header>
    <h1>EU countries</h1>
  </header>
  <section class="countries">
    <div
      class="countries-wrapper"
      v-for="(country, idx) in countries"
      :key="idx"
    >
      <div class="card">
        <img :src="country.flag" />
        <div class="card-body">
          <h2>{{ country.name }}</h2>
          <p>IS0: {{ country.iso2 }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import countries from "./assets/countries";
export default {
  name: "EUMainPage",

  data() {
    return {
      countries: [],
    };
  },
  created() {
    this.countries = countries;
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

header {
  text-align: center;
  font-size: 4vmin;
}

.countries {
  min-height: 70vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
}

.card {
  width: 300px;
  height: 189px;
  cursor: pointer;
  border-radius: 16px;
  box-shadow: 0 0 13px 0px rgba(0, 0, 0, 0.3);
  transition: 0.5s;
  overflow: hidden;
  margin: 0.85rem;
}

.card:hover {
  height: 280px;
}

.card img {
  width: 302px;
  height: 189px;
  border-radius: 16px;
  transition: 0.5s;
}

.card:hover img {
  border-radius: 16px 16px 0 0;
}

.card .card-body {
  padding: 0.5rem 0.85rem 1rem;
  height: 0;
}

.card .card-body h2 {
  margin: 0.5rem 0;
  font-size: 0.85rem;
  color: hsl(240, 27%, 39%);
  letter-spacing: 3px;
}

.card .card-body p {
  text-align: justify;
  font-size: 0.9rem;
  line-height: 25px;
}
</style>
