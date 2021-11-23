<template>
  <div id="app">
    <div class="card">
      <!-- Custom information -->
      <div class="about">
        <h3>Chart.js</h3>
        <p class="lead">Blend mode: multiply</p>
        <div class="legends">
          <div class="info">
            <span class="legend legend--this"></span>
            <p>This week</p>
          </div>
          <div class="info">
            <span class="legend legend--prev"></span>
            <p>Previous week</p>
          </div>
        </div>
      </div>

      <!-- Canvas for Chart.js -->
      <line-chart></line-chart>

      <!-- Custom Axis -->
      <div class="axis">
        <div class="tick">
          MON
          <span class="value value--this">24</span>
          <span class="value value--prev">20</span>
        </div>
        <div class="tick">
          TUE
          <span class="value value--this">18</span>
          <span class="value value--prev">22</span>
        </div>
        <div class="tick">
          WED
          <span class="value value--this">16</span>
          <span class="value value--prev">30</span>
        </div>
        <div class="tick">
          THU
          <span class="value value--this">18</span>
          <span class="value value--prev">22</span>
        </div>
        <div class="tick">
          FRI
          <span class="value value--this">24</span>
          <span class="value value--prev">18</span>
        </div>
        <div class="tick">
          SAT
          <span class="value value--this">36</span>
          <span class="value value--prev">22</span>
        </div>
        <div class="tick">
          SUN
          <span class="value value--this">28</span>
          <span class="value value--prev">30</span>
        </div>
      </div>
    </div>
    <area-chart class="area-chart-wrapper"></area-chart>
    <pie-chart></pie-chart>
    <bar-chart></bar-chart>
    <radar-chart></radar-chart>
  </div>
</template>

<script>
import AreaChart from "./components/AreaChart.vue";
import PieChart from "./components/PieChart.vue";
import BarChart from "./components/BarChart.vue";
import RadarChart from "./components/RadarChart.vue";
import LineChart from "./components/LineChart.vue";

export default {
  name: "App",
  components: {
    LineChart,
    AreaChart,
    PieChart,
    BarChart,
    RadarChart,
  },
  data() {
    return {
      chartData: {
        Books: 24,
        Magazine: 30,
        Newspapers: 10,
      },
    };
  },
};
</script>

<style>
body {
  background-color: #f3f5f7;
  font-family: "Helvetica Neue", Arial, sans-serif;
}

.card {
  background-color: #fff;
  box-shadow: 0 0 6px rgba(0, 0, 0, 0.1);
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  max-width: 500px;
  height: 500px;
  border-radius: 10px;
  overflow: hidden;
}

.card .about {
  height: 225px;
  padding: 20px;
  box-sizing: border-box;
}

.card .about h3,
.card .about .lead {
  font-weight: 300;
  margin: 0;
}

.card .about h3 {
  font-size: 24px;
}

.card .about .lead {
  color: #aaa;
}

.card .info {
  float: left;
  padding: 10px 30px 10px 0;
}

.card .info p {
  font-size: 11px;
  color: #aaa;
  font-weight: 300;
}

.legends {
  padding-top: 20px;
  overflow: hidden;
}

.legend {
  display: block;
  width: 8px;
  height: 8px;
  margin-top: 15px;
  margin-bottom: 15px;
  border-radius: 50%;
}

.legend--this {
  background-color: #5555ff;
}

.legend--prev {
  background-color: #ff55b8;
}

.axis {
  position: absolute;
  color: #fff;
  z-index: 1;
  text-transform: uppercase;
  display: flex;
  width: 100%;
  bottom: 0;
}

.axis .tick {
  flex: 1;
  position: relative;
  overflow: hidden;
  opacity: 0.2;
  font-size: 11px;
  text-align: center;
  line-height: 40px;
  padding-top: 150px;
}

.axis .tick:hover {
  opacity: 1;
  background-color: rgba(255, 255, 255, 0.2);
}

.axis .tick .value {
  transform: translateY(-40px);
  transition: 0.3s transform;
  position: absolute;
  top: 20px;
  color: #444;
  border-radius: 2px;
  width: 100%;
  line-height: 20px;
}

.axis .tick:hover .value.value--this {
  transform: translateY(0);
  display: block;
}

.value.value--this {
  color: #5555ff;
  font-weight: bold;
}

.area-chart-wrapper{
  position: relative;
  top: 100px;
}
</style>
