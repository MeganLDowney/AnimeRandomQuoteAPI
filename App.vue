<template>
  <h1>Anime Quotes</h1>
  <h2>Character:</h2>
  <p>{{ quote.character }}</p>
  <h2>Anime:</h2>
  <p>{{ quote.anime }}</p>
  <h2>Quote:</h2>
  <p>{{ quote.quote }}</p>
</template>

<script>
export default {
  data: function () {
    return {
      quote: "",
    };
  },
  methods: {
    async getQuote() {
      const res = await fetch("https://animechan.xyz/api/random");
      const quote = await res.json();
      this.quote = quote;
      console.log(quote);
    },
  },
  created() {
    this.getQuote(this.quote);
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Acme&family=BIZ+UDGothic&family=Londrina+Outline&family=Pompiere&family=Rampart+One&family=Tourney:wght@100&display=swap");
#app {
  font-family: "BIZ UDGothic", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin-top: 20px;
  background-color: #858585;
  padding: 15px;
  border-radius: 20px;
}
h1 {
  font-size: 3em;
}
</style>
