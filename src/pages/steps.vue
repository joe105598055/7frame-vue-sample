<template>
  <f7-page name="steps">
    <f7-navbar title="Steps"></f7-navbar>
    <f7-block-title>Step Example</f7-block-title>
    <f7-block strong>
      <f7-link href="/step1/">Go Step1</f7-link>
    </f7-block>
    <f7-block>
      <canvas id="myChart" width="400" height="400"></canvas>
    </f7-block>
  </f7-page>
</template>
<script>
// var Chart = require('chart.js');
import Chart from "chart.js";
export default {
  data() {
    return {
      name: "",
      email: "",
      gender: "",
      toggle: "",
      range: 50
    };
  },
  mounted() {
    console.log(`[setting]`);
    this.$nextTick(() => {
      var ctx = document.getElementById("myChart");
      var myChart = new Chart(ctx, {
        type: "bar",
        data: {
          labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange"],
          datasets: [
            {
              label: "# of Votes",
              data: [12, 19, 3, 5, 2, 3],
              backgroundColor: [
                "rgba(255, 99, 132, 0.2)",
                "rgba(54, 162, 235, 0.2)",
                "rgba(255, 206, 86, 0.2)",
                "rgba(75, 192, 192, 0.2)",
                "rgba(153, 102, 255, 0.2)",
                "rgba(255, 159, 64, 0.2)"
              ],
              borderColor: [
                "rgba(255,99,132,1)",
                "rgba(54, 162, 235, 1)",
                "rgba(255, 206, 86, 1)",
                "rgba(75, 192, 192, 1)",
                "rgba(153, 102, 255, 1)",
                "rgba(255, 159, 64, 1)"
              ],
              borderWidth: 1
            }
          ]
        },
        options: {
          scales: {
            yAxes: [
              {
                ticks: {
                  beginAtZero: true
                }
              }
            ]
          }
        }
      });
    });
  },
  methods: {
    submit() {
      this.$f7.dialog.alert(
        "Uesrname: " +
          this.name +
          "<br>email: " +
          this.email +
          "<br>Gender: " +
          this.gender +
          "<br>Toggle: " +
          this.toggle +
          "<br>Range: " +
          this.range
      );
    },
    changeRang(value) {
      this.range = value;
    }
  }
};
</script>
