<template lang="">
    <div v-bind:class="theme">
      <h1>{{title}}</h1>
        <form @submit.prevent="searchMovie">
            <input
                type="text"
                placeholder="Search for a movie"
                v-model="movie"
            />
            <input type="submit" value="search" />

            <p>Using mustaches: {{ rawHtml }}</p>
            <p>Using v-html directive: <span v-html="rawHtml"></span></p>
            <ol>
                <li v-bind:key="mov.name" v-for="mov in movies">
                    {{ mov }}
                </li>
            </ol>
        </form>
        <h3>change Theme</h3>
        <button v-on:click="changeTheme">Change</button>
        <p v-if="ask" v-on:click="show">am i visable</p>
        <select v-model="selected">
            <option disabled value="">Please select one</option>
            <option>A</option>
            <option>B</option>
            <option>C</option>
        </select>
        <span>Selected: {{ selected }}</span>
    </div>
</template>
<script>
export default {
  props: ["title"],
  name: "SearchMovie",
  data() {
    return {
      selected: "",
      ask: true,
      theme: "light",
      rawHtml: "<h1>apple</h1>",
      movie: "",
      movies: [{ movie1: "thisMovie" }],
    };
  },
  methods: {
    async searchMovie() {
      this.movies.push({ movie2: "the new movie" });
      // const url = new URL("https://imdb8.p.rapidapi.com/auto-complete");
      // const params = { q: this.movie };
      // url.search = new URLSearchParams(params).toString();
      // const response = await fetch(url, {
      //   method: "GET",
      //   headers: {
      //     "x-rapidapi-host": "imdb8.p.rapidapi.com",
      //     "x-rapidapi-key":
      // shit left my keys at home
      //   },
      // });
      // const data = await response.json();
      // this.movies.push(data);
    },
    changeTheme() {
      if (this.theme === "light") {
        this.theme = "dark";
      } else {
        this.theme = "light";
      }
    },
    show() {
      this.ask = !this.ask;
    },
  },
};
</script>
<style scoped>
.light {
  background-color: #eeeeee;
}
.dark {
  background-color: black;
  color: white;
}
</style>
