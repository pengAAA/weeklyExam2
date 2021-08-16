<template>
  <div class="time-wrap">
    <!-- <div class="time-num">
      <input class="minutes" v-model="val" />:
      <input class="seconds" v-model="val" />:
      <input class="millisecond" v-model="val" />
    </div> -->
    <div class="time-num">
      <span class="minutes">{{ minute }}</span>:
      <span class="seconds">{{ second }}</span>:
      <span class="millisecond">{{ millisecond }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "MajorClock",
  props: {
    value: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      val: this.value,
      timer: "",
      minute: 0,
      second: 0,
      millisecond: 0,
    };
  },
  watch: {
    // value(newValue) {
    //   this.val = newValue
    // },
    // val (newValue) {
    //   this.$emit('input', newValue === 100 ? 0 : newValue)
    // },
    minute: {
      handler(newVal) {
        this.num(newVal);
      },
    },
    second: {
      handler(newVal) {
        this.num(newVal);
      },
    },
    millisecond: {
      handler(newVal) {
        this.num(newVal);
      },
    },
  },
  methods: {
    num(n) {
      return n < 10 ? "0" + n : "" + n;
    },
    start() {
      let that = this
      that.timer = window.setInterval(()=> {
        if (that.millisecond === 100) {
          that.millisecond = 0
          that.second += 1
        } else if (that.second === 60) {
          that.millisecond = 0
          that.second = 0
          that.hours += 1
        } else {
          that.millisecond += 1
        }
      },10)
    },
  },
};
</script>

<style scoped>
.time-wrap {
  background-color: #000;
  color: #fff;
  padding: 20px 0;
}
.time-num {
  display: flex;
  justify-content: space-evenly;
}
input {
  width: 33%;
}
</style>