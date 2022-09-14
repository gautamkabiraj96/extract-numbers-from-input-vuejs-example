<template>
  <div id="app">
    <input
      type="text"
      placeholder="Type something..."
      v-model="userInputValue"
    />
    <p>User input: {{ userInputValue }}</p>
    <h3>Parsed value: {{ parsedInputValue }}</h3>
    <!--
      www.nightprogrammer.com
    -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      userInputValue: "",
    };
  },
  computed: {
    parsedInputValue() {
      let str = this.userInputValue;
      let matches = str.match(/\d+/g);
      let matchedString = "";

      if (matches && matches.length) {
        matches.forEach((m) => {
          matchedString += m;
        });
      }

      return matchedString;
    },
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 24px;
  background: rgb(238, 238, 238);
}
</style>
