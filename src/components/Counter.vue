<template>
  <h2>{{ customTitle }}</h2>
  <p>{{ counter }} <sup>2</sup>={{ squareCounter }}</p>
  <div>
    <button class="btn" @click="getIncrease">+1</button>
    <button class="btn" @click="getDecrease">-1</button>
  </div>
</template>

<script>
export default {
  name: "Counter",
  props: {
    title: String,
    start: {
      type: Number,
      default: 100,
      validator(value) {
        return value >= 0;
      },
    },
  },
  data() {
    return {
      counter: this.start,
    };
  },
  methods: {
    getSquareValue() {
      console.log("getSquareValue");
      return this.counter * this.counter;
    },
    getIncrease() {
      return this.counter++;
    },
    getDecrease() {
      return this.counter--;
    },
  },
  computed: {
    squareCounter() {
      console.log("computed squareCounter");
      return this.counter * this.counter;
    },
    customTitle() {
      return this.title ? this.title : "Counter";
    },
  },
};
</script>

<style scoped>
.btn {
  background-color: #64b687;
  border-radius: 10px;
  border: 1px solid #fff;
  color: #fff;
  transition: 03s ease-in-out;
  cursor: pointer;
  margin: 0 5px;
  padding: 5px 15px;
}

.btn:hover {
  background-color: #58d68e;
  transition: 0.3s ease-in-out;
}
</style>>

