<template>
  <div>
    <input type="text" id="fname" name="fname" v-model="url" />

    <button v-if="url" type="button" @click="callApi">Click Me!</button>

    <p>here be dragons</p>
    <code>{{ result }}</code>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      url: null,
      result: null,
    };
  },
  methods: {
    callApi() {
      axios.get(this.url).then((r) => {
        this.result = r.data;
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
