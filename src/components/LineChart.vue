<script>
import { Line } from "vue-chartjs";

export default {
  extends: Line,
  mounted() {
    this.gradientThisWeek = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 150);
    this.gradientPrevWeek = this.$refs.canvas
      .getContext("2d")
      .createLinearGradient(0, 0, 0, 150);

    this.gradientThisWeek.addColorStop(0, "#5555FF");
    this.gradientThisWeek.addColorStop(1, "#9787FF");

    this.gradientPrevWeek.addColorStop(0, "#FF55B8");
    this.gradientPrevWeek.addColorStop(1, "#FF8787");
    this.renderChart(
      {
        labels: ["MON", "TUE", "WED", "THU", "FRI", "SAT", "SUN"],
        datasets: [
          {
            label: "This week",
            data: [24, 18, 16, 18, 24, 36, 28],
            backgroundColor: this.gradientThisWeek,
            borderColor: "transparent",
            pointBackgroundColor: "#FFFFFF",
            pointBorderColor: "#FFFFFF",
            lineTension: 0.4,
          },
          {
            label: "Previous week",
            data: [20, 22, 30, 22, 18, 22, 30],
            backgroundColor: this.gradientPrevWeek,
            borderColor: "transparent",
            pointBorderColor: "#000000",
            lineTension: 0.4,
          },
        ],
      },
      {
        responsive: false,
        maintainAspectRatio: false,
        title: {
          display: true,
          text: "My Data",
        },
        elements: {
          point: {
            radius: 0,
            hitRadius: 5,
            hoverRadius: 5,
          },
        },
        legend: {
          display: false,
        },
        scales: {
          xAxes: [
            {
              display: false,
            },
          ],
          yAxes: [
            {
              display: false,
              ticks: {
                beginAtZero: true,
              },
            },
          ],
        },
      }
    );
  },
};
</script>
