<template>
  <div class="container">
    <v-row>
      <v-col cols="12" sm="6" md="6">
        <v-card class="speedometer" elevation="2"> 


      
      </v-card>
      </v-col>

      <v-col cols="6" md="6">
        <v-card class="users-activity" height="428">
          <!-- Componente V-Card que contem a chamada da biblioteca de gráficos colunas -->
          <v-row>
            <v-col md="12">
              <v-card-title>Users Activity</v-card-title>
              <!-- Div de chamada do gráfico de colunas, onde são estabelecidos os seus parametros. -->
              <div id="chart">
                <apexchart
                  type="bar"
                  height="350"
                  :options="chartOptions"
                  :series="series"
                ></apexchart>
              </div>
            </v-col>
          </v-row>
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
          name: "Sent",
          data: [200, 70, 180, 180, 80, 70, 150],
        },
        {
          name: "Recieved",
          data: [100, 70, 50, 80, 40, 70, 70],
        },
      ],
      chartOptions: {
        chart: {
          height: 350,
          type: "bar",
          stacked: true,
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

        colors: ["#7900f9", "#00bdf1"],

        plotOptions: {
          bar: {
            horizontal: false,
            borderRadius: 20,
          },
        },

        grid: {
          borderColor: "#000",
          row: {
            colors: ["#fff", "transparent"], // takes an array which will be repeated on columns
            opacity: 0.5,
          },
        },
        markers: {
          size: 4,
        },
        xaxis: {
          categories: ["M", "T", "W", "T", "F", "S", "S"],
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
          show: true,
        },
        legend: {
          position: "top",
          horizontalAlign: "center",
          floating: true,
          offsetY: -25,
          offsetX: -5,
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
.users-activity {
  margin-top: 13px;
}
</style>