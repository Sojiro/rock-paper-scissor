<template>
  <h1>You</h1>
  <div class="option-container">
    <div
      class="option"
      v-for="option in options"
      :key="option"
      @click="select(option)"
    >
      <span>
        {{ option }}
      </span>
    </div>
  </div>
  <hr />
  <h1>AI</h1>
  <div class="option-container">
    <div class="option" v-if="aiOption">
      <span>
        {{ aiOption }}
      </span>
    </div>
  </div>
</template>

<script>
import { ref } from "@vue/reactivity";

export default {
  name: "App",
  components: {},
  setup() {
    const options = ["Rock", "Paper", "Scissor"];
    const aiOption = ref("");
    return { options, aiOption };
  },
  methods: {
    select() {
      this.aiOption =
        this.options[Math.floor(Math.random() * this.options.length)];
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.option-container {
  display: flex;
  justify-content: center;
  align-content: center;
  gap: 50px;
}

.option {
  width: 100px;
  height: 100px;
  user-select: none;
  cursor: pointer;
  border: 2px solid gray;
  border-radius: 100%;
  display: flex;
  flex-direction: column;
  align-content: center;
  justify-content: center;
  align-items: center;
  box-shadow: 5px 7px 15px 5px darkgrey;
}
</style>
