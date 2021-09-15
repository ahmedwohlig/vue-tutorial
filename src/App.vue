<template>
  <div id="app">
    <!-- <HelloWorld title="whatsUpp" /> -->
    <Cards
      v-for="cd in da"
      v-bind:key="cd.name"
      v-bind:name="cd.name"
      v-bind:details="cd.details"
      v-bind:footer="cd.footer"
      class="a-card"
    />
  </div>
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import Cards from "./components/Cards.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    Cards,
  },
  data() {
    return {
      da: [
        { name: "apple", details: "the details", footer: "the footer details" },
        { name: "node", details: "the details", footer: "the footer details" },
        {
          name: "supper",
          details: "the details",
          footer: "the footer details",
        },
        { name: ".net", details: "the details", footer: "the footer details" },
        { name: "java", details: "the details", footer: "the footer details" },
        {
          name: "application",
          details: "the details",
          footer: "the footer details",
        },
        {
          name: "merchant",
          details: "the details",
          footer: "the footer details",
        },
        {
          name: "banana",
          details: "the details",
          footer: "the footer details",
        },
      ],
    };
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: row;
}
</style>
