<template>
  <!-- Upper -->
  <h1>Hello vue</h1>
  <div>
    <div class="d-f up-up">
      <p>Show the Price Well</p>
      <input type="text" v-model="price" required />
    </div>

    <div class="d-f up-lower">
      <p>Comma Separated:</p>
      <div>{{ Number(price).toLocaleString() }}</div>
    </div>
  </div>

  <!-- Lower -->

  <div class="d-f lower">
    <div class="left">
      <h2>All</h2>
      <ul>
        <li v-for="(item, index) in contents1" :key="index">{{ item }}</li>
      </ul>
    </div>

    <div class="right">
      <h2>Fulfilled</h2>
      <ul>
        <li v-for="(item, index) in contents2" :key="index">{{ item }}</li>
      </ul>

      <div v-if="showContent" class="toggleMessage">
        <h2>Upcoming...</h2>
        <ul>
          <li v-for="(item, index) in contents3" :key="index">{{ item }}</li>
        </ul>
      </div>

      <button @click="toggle">
        <span v-if="showContent">Show Upcoming</span>
        <span v-if="!showContent">Hide Upcoming</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data() {
    return {
      showContent: false,
      price: "40000",
      contents1: [
        ".vue",
        "{ { } }",
        "data",
        "v-bind",
        "v-for",
        "computed",
        "v-if",
        "v-show",
        "v-model",
        "v-on",
        "methods",
        "props",
        "typed-props",
        "mounted",
        "axios"
      ],
      contents2: [
        ".vue",
        "{ { } }",
        "data",
        "v-bind",
        "v-for",
        "computed",
        "v-if",
        "v-show",
        "v-model",
        "v-on",
        "methods"
      ],
      contents3: ["props", "typed-props", "mounted", "axios"]
    };
  },
  methods: {
    toggle() {
      this.showContent = !this.showContent;
    }
  }
};
</script>

<style scoped>
#app {
  text-align: left;
}

.d-f {
  display: flex;
  align-items: center;
}

.up-up {
  height: 40px;
}

.up-up input {
  height: 18px;
  font-size: 16px;
  margin-left: 5px;
}

.up-lower {
  height: 40px;
}
.up-lower div {
  margin-left: 5px;
}

.lower {
  align-items: flex-start;
}

.right {
  margin-left: 30px;
}
</style>
