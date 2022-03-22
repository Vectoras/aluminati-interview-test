<template>
  <div>
    <div
      v-for="number in numbers"
      :key="number.value"
      class="number"
      :class="{ active: number.isActive }"
      :id="'number-' + number.value"
      @mouseenter="hov(number.value)"
      @mouseleave="reset"
    >
      {{ number.value }}
    </div>
  </div>
</template>

<script>
export default {
  name: "AppNumbers",
  data() {
    return {
      numbers: []
    };
  },
  props: {
    limit: {
      required: true
    }
  },
  watch: {
    limit: {
      handler(newLimit) {
        let numbers = [];
        for (let i = 1; i <= newLimit; i++) {
          numbers.push({ value: i, isActive: false });
        }

        this.numbers = numbers.sort(() => Math.random() - 0.5);
      },
      immediate: true
    }
  },
  methods: {
    hov(refValue) {
      this.numbers.forEach((number, index, array) => {
        if (number.value != refValue && refValue % number.value == 0)
          array.splice(index, 1, { value: number.value, isActive: true });
      });
    },
    reset() {
      this.numbers.forEach((number, index, array) => {
        array.splice(index, 1, { value: number.value, isActive: false });
      });
    }
  }
};
</script>

<style scoped>
.number {
  display: inline-block;
  padding: 5px;
  background-color: lightgrey;
  margin: 5px;
  cursor: help;
}

.active {
  background-color: red;
}
</style>
