<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1 :style="{ backgroundColor: color }">{{ title }}</h1>
    <h1>{{ other }}</h1>
    <h1 @click="attachRed = !attachRed" :class="{ red: attachRed }">
      {{ sayHello() }}
    </h1>
    <p v-if="attachRed">show red</p>
    <p v-else>not red</p>
    <v-btn
      color="success"
      @click="
        {
          counter++;
        }
      "
      >{{ counter }}</v-btn
    >
    <v-btn outline color="primary" dark>text</v-btn>
    <input v-model="color" type="text" />
    <ul>
      <li v-for="(person, i) in persons" :key="person.id">
        {{ person }} {{ i }}
      </li>
    </ul>
    <ul>
      <li v-for="i in 10" v-bind:key="i">
        <p>{{ i }}</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      title: "hello the world!!! as title",
      other: "other hello 22",
      attachRed: false,
      color: "gray",
      counter: 0,
      persons: ["Pierre", "Fréd", "Luc", "Barbara"]
    };
  },
  methods: {
    sayHello() {
      return "Hello as a function 8";
    }
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
