<template>
  <div class="container">
    <!-- Componente V-Card que contem a chamada da biblioteca de gráficos de linha -->
    <v-row>
      <v-col cols="12" sm="6" md="8">
        <v-card class="sales-information" elevation="2">
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
        <v-card class="emails-sent" height="428">
          <!-- Componente V-Card que contem a chamada da biblioteca de gráficos Radiais -->
          <v-row>
            <v-col md="6">
              <v-card-title>E-mails Sent</v-card-title>
              <!-- Div de chamada do gráfico radial, onde são estabelecidos os seus parametros. -->
              <div class="radail-circle" id="chart-radial">
                <apexchart
                  type="radialBar"
                  width="250"
                  :options="chartOptionsRadial"
                  :series="seriesRadial"
                ></apexchart>
              </div>
            </v-col>

            <v-col md="5">
              <v-row>
                <div class="week">
                  <v-btn text plain>This Week</v-btn>
                  <div class="informations">
                    <v-card-text class="informations">
                       <span class="sent"></span>Sent: <strong>345</strong><br>
                       <span class="Recieved"></span>Recieved: <strong>194</strong>
                    </v-card-text>
                  </div>
                </div>
              </v-row>
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
        labels: ["Sent", "Recieved"],
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
  margin-left: -30px;
}
.emails-sent {
  margin-top: 13px;
}
.week {
  position: absolute;
  margin-top: 23px;
  right: 10px;
}
.informations {
  margin-top: 100px;
}
.sent {
  background: #7900f9;
  color: #7900f9;
  height: 12px;
  width: 12px;
  left: 0px;
  top: 0px;
  border-width: 0px;
  border-color: rgb(255, 255, 255);
  border-radius: 12px;
  position: relative;
  display: inline-block;
  cursor: pointer;
  margin-right: 3px;
  border-style: solid;
}
.Recieved {
  background: #00bdf1;
  color: #00bdf1;
  height: 12px;
  width: 12px;
  left: 0px;
  top: 0px;
  border-width: 0px;
  border-color: rgb(255, 255, 255);
  border-radius: 12px;
  position: relative;
  display: inline-block;
  cursor: pointer;
  margin-right: 3px;
  border-style: solid;
}
</style>