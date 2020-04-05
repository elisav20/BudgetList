<template>
  <div class="total-value" :class="changeClass()">Balance: {{ total }}</div>
</template>

<script>
export default {
  name: 'TotalBalance',
  props: {
    total: {
      type: Number,
      default: 0
    }
  },
  methods: {
    changeClass() {
      if(this.total === 0) {
        return 'text-black';
      } else if(this.total > 0) {
        return 'text-green';
      } else if (this.total < 0) {
        return 'text-red';
      }
    }
  }
}
</script>

<style scoped>
  .total-value {
    font-size: 26px;
    text-transform: uppercase;
    padding: 20px;
    text-align: center;
  }

  .text-green {
    color: green;
  }

  .text-black {
    color: black;
  }

  .text-red {
    color: red;
  }
</style>