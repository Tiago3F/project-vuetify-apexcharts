<template>
  <div class="container">
    <!-- Componente V-Card que contem a chamada da biblioteca de gráficos de linha -->
    <v-row>
      <v-col cols="12" sm="6" md="8">
        <v-card class="sales-information" elevation="2" >
          <v-card-title>
            <h1>$38,4K</h1>
          </v-card-title>
          <!-- Div de chamada do gráfico de linha, onde são estabelecidos os seus parametros. -->
          <div class="ml-5" id="chart-line">
            <apexchart
              type="line"
              height="350"
              :options="chartOptions"
              :series="series"
            ></apexchart>
          </div>
        </v-card>
      </v-col>

      <v-col cols="6" md="4">
        <!-- Componente V-Card que contem a chamada da biblioteca de gráficos Radiais -->
        <v-card class="emails-sent" elevation="2" height="428">
          <v-row>
            <v-col>
              <v-card-title>E-mail Sent</v-card-title>
            </v-col>
            <v-btn class="mt-7 mr-5" text plain>This Week</v-btn>
          </v-row>
           <!-- Div de chamada do gráfico radial, onde são estabelecidos os seus parametros. -->
          <div class="radail-circle" id="chart-radial">
            <apexchart
              type="radialBar"
              width="250"
              :options="chartOptionsRadial"
              :series="seriesRadial"
            ></apexchart>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>




<script>
export default {
  components: {
    VueApexCharts: () => import("vue-apexcharts"),
  },
  data() {
    return {
      series: [
        {
          name: "Total",
          data: [28, 29, 33, 36, 32, 32],
        },
        {
          name: "Pipeline",
          data: [12, 11, 14, 18, 17, 13],
        },
      ],
      chartOptions: {
        chart: {
          height: 350,
          type: "line",
          dropShadow: {
            enabled: true,
            color: "#000",
            top: 18,
            left: 7,
            blur: 10,
            opacity: 0.2,
          },
          toolbar: {
            show: false,
          },
        },
        colors: ["#00bdf1", "#7900f9"],

        stroke: {
          curve: "smooth",
        },
        title: {
          text: "Overal Revenue",
          align: "left",
        },
        grid: {
          borderColor: "#fff",
          row: {
            colors: ["#fff", "transparent"], // takes an array which will be repeated on columns
            opacity: 0.5,
          },
        },
        markers: {
          size: 4,
        },
        xaxis: {
          categories: ["SEP", "OCT", "NOV", "DEC", "JAN", "FEB"],
          axisBorder: {
            show: true,
            color: "#fff",
            height: 0,
            width: "100%",
            offsetX: 0,
            offsetY: 0,
          },
        },
        yaxis: {
          show: false,
        },
        legend: {
          position: "top",
          horizontalAlign: "center",
          floating: true,
          offsetY: -25,
          offsetX: -5,
        },
      },
      seriesRadial: [80, 55],
      chartOptionsRadial: {
        chart: {
          height: 350,
          type: "radialBar",
        },
        plotOptions: {
          radialBar: {
            dataLabels: {
              name: {
                fontSize: "16px",
              },
              value: {
                fontSize: "16px",
              },
            },
          },
        },
        labels: ["Sent", "Received"],
        colors: ["#7900f9", "#00bdf1"],
        stroke: {
          lineCap: "round",
        },
      },
    };
  },
};
</script>

<style scoped>
.container {
  font-family: sans-serif;
}
.radail-circle {
  margin-top: 50px;
  margin-left: -40px;
}
.emails-sent {
  margin-top: 13px;
}
</style>