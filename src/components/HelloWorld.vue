<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ title }}</h1>
    <h1>{{ other }}</h1>
    <h1 @click="attachRed = !attachRed" :class="{ red: attachRed }">
      {{ sayHello() }}
    </h1>
    <p>{{ counter }}</p>
    <v-btn outline color="primary" dark>text</v-btn>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: () => ({
    title: "hello the world!!! as title",
    other: "other hello 22",
    attachRed: false
  }),
  methods: {
    sayHello: () => "Hello as a function"
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
.red {
  color: red;
}
</style>
