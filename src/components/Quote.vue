<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="card">
      <div class="card-body quote">
        <slot></slot>
      </div>
      <!-- <div class="quotes">
        <h1>Quotes Added</h1>
        <div class="progress-bar">
          <span class="bar-text" >{{ barValue }} / {{ maxBarValue }}</span>
          <div class="line" :style="{ width: barWidth + '%'}"></div>
        </div>
      </div>
      <button type="submit" @click="addQuotes" >Add Quote</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name: 'Quotes',
  data() {
    return {
      barValue: 0,
      maxBarValue: 10,
      barWidth: 0
    };
  },
  methods: {
    addQuotes() {
      this.barValue++;
      this.barWidth += 10;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.progress-bar {
  background-color: #ececec;
  border-radius: 10px;
  height: 30px;
  margin: 20px 0;
  position: relative;
  width: 100%;

  .bar-text {
    color: black;
    line-height: 30px;
    position: absolute;
    text-align: center;
    width: 100%;
  }
}
.line {
  background-color: #b4b4f4;
  height: 100%;
  max-width: 100%;
  min-width: 0;
}
.quote {
  cursor: pointer;
}
.quote:hover {
  background-color: #ffe2e2;
}
</style>
