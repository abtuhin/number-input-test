<template>
  <div class="number-input">
    <div v-for="(input, index) in inputs" :key="index">
      <input type="number" v-model="inputs[index]" />
    </div>
    <button @click="addInput">{{ sum }}</button>
  </div>
</template>

<script>
export default {
  name: "NumberInput",
  data: function () {
    return {
      inputs: [10, 20, 25, 25, 20],
    };
  },
  computed: {
    sum() {
      return this.inputs
        .filter((val) => val !== "")
        .reduce((sum, cur) => parseInt(sum) + parseInt(cur), 0);
    },
  },
  methods: {
    random() {
      return Math.floor(Math.random() * 10 + 1);
    },
    addInput() {
      this.inputs.push(this.random());
    },
  },
};
</script>

<style scoped>

button {
  margin-top: 30px;
  width: 510px;
  height: 40px;
}

input {
  margin: 5px;
  height: 40px;
  width: 500px;
}
</style>
