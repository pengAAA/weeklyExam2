<template>
  <div class="fun-wrap" v-if="flag === true">
    <a href="javascript:;" class="metering" @click="restart">复位</a>
    <div class="dottes">
      <span class="dot"></span>
      <span class="dot"></span>
    </div>
    <a href="javascript:;" class="start" @click="start">启动</a>
  </div>
  <div class="fun-wrap" v-else>
    <a href="javascript:;" class="metering" @click="metering">计次</a>
    <div class="dottes">
      <span class="dot"></span>
      <span class="dot"></span>
    </div>
    <a href="javascript:;" class="stop" @click="stop">停止</a>
  </div>
</template>

<script>
export default {
  name: "ControlButtons",
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
    start() {
      if (this.flag === true) {
        this.flag = false;
      }
    },
    restart() {
      this.flag = true;
    },
    stop() {
      this.flag = true;
    },
    metering() {
      this.flag = true
    }
  },
};
</script>

<style scoped>
.fun-wrap {
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: #000;
}
a {
  display: block;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  text-align: center;
  line-height: 40px;
  font-size: 12px;
  text-decoration: none;
}
a.start {
  background-color: rgba(0, 255, 0, 0.7);
  color: #fff;
}
a.metering {
  background-color: rgba(255, 255, 255, 0.8);
  color: #fff;
}
a.stop {
  background-color: rgba(255, 0, 0, 0.7);
  color: #f00;
}
.dot {
  display: inline-block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background-color: #eee;
  margin: 0 5px;
}
</style>