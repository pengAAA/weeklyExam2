<template>
  <ul class="count-list"></ul>
</template>

<script>
export default {
  name: "SplitTimes",
  props: {
    value: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      val: this.value,
      flag: true,
    };
  },
  methods: {
    
  },
};
</script>

<style scoped>
.count-list {
  background-color: #000;
}
</style>