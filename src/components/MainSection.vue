<template>
  <!-- First Row of main section -->
  <div class="first-box-container">
    <div class="box-item" v-for="(rowData, index) in firstRowData" :key="index">
      <div class="space-between">
        <div class="box-title">{{ rowData.name }}</div>
        <i :class="rowData.icon" class="icon-background"></i>
      </div>
      <div class="box-price">{{ rowData.price }}</div>
      <div>
        <span class="green-color"
          ><i :class="rowData.percentageIcon"></i> {{ rowData.percentage }}
        </span>
        <span class="box-text"> Since last week</span>
      </div>
    </div>
  </div>
  <!-- Second Row of main section -->
  <div class="second-row-box-container">
    <div class="second-row-box-item">
      <div class="box-title margin-between">Recent Workflow</div>
      <span class="green-color"
        ><i class="fa-solid fa-arrow-trend-up"></i> 17%</span
      >
      <Line
        id="my-line-chart-id"
        class="line-chart"
        :options="lineChartOptions"
        :data="lineChartData"
      ></Line>
    </div>
    <div class="second-row-box-item">
      <div class="box-title margin-between">Recent Marketing</div>
      <span class="green-color"
        ><i class="fa-solid fa-arrow-trend-up"></i> 17%</span
      >
      <Bar
        id="my-bar-chart-id"
        class="bar-chart"
        :options="barChartOptions"
        :data="barChartData"
      />
    </div>
  </div>
  <!-- Third row of main section -->
  <div class="third-row-box-container">
    <div class="third-row-box-item">
      <div class="table-content">
        <div class="space-between">
          <div class="box-title">Document</div>
          <button class="time-period-drop-down">
            Weekly <i class="fa fa-fw fa-caret-down"></i>
          </button>
        </div>
        <span class="box-text">Document tracking information</span>
      </div>
      <table>
        <tr>
          <th v-for="header in tableHeader" :key="header.key">
            {{ header.name }}
          </th>
        </tr>
        <tr>
          <td>Annual Report</td>
          <td>PDF</td>
          <td>Property</td>
          <td>Dianna Mathews</td>
          <td><button class="send-btn">Send</button></td>
        </tr>
        <tr>
          <td>Business Plan</td>
          <td>WORD</td>
          <td>Cryptocurrency</td>
          <td>Philip James</td>
          <td><button class="send-btn">Send</button></td>
        </tr>
        <tr>
          <td>Marketing Tool</td>
          <td>PDF</td>
          <td>Content Creator</td>
          <td>Amanda Ross</td>
          <td><button class="pending-btn">Pending</button></td>
        </tr>
      </table>
    </div>
  </div>
</template>
<script>
import { Bar, Line } from "vue-chartjs";
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
  PointElement,
  LineElement,
} from "chart.js";

ChartJS.register(
  BarElement,
  CategoryScale,
  LinearScale,
  Title,
  Tooltip,
  Legend,
  PointElement,
  LineElement
);
export default {
  components: {
    Bar,
    Line,
  },
  data() {
    return {
      barChartData: {
        labels: [
          "Jan",
          "Feb",
          "Mar",
          "Apr",
          "May",
          "Jun",
          "Jul",
          "Aug",
          "Sep",
          "Oct",
          "Nov",
          "Dec",
        ],
        datasets: [
          {
            data: [40, 20, 12, 15, 30, 50, 5, 10, 25, 35, 60, 90],
            backgroundColor: "blue",
            label: "Data One",
          },
        ],
      },
      barChartOptions: {
        responsive: true,
      },
      lineChartData: {
        labels: [
          "Jan",
          "Feb",
          "Mar",
          "Apr",
          "May",
          "Jun",
          "Jul",
          "Aug",
          "Sep",
          "Oct",
          "Nov",
          "Dec",
        ],
        datasets: [
          {
            data: [40, 20, 12, 15, 30, 50, 5, 10, 25, 35, 60, 90],
            backgroundColor: "blue",
            label: "Data One",
          },
        ],
      },
      lineChartOptions: {
        responsive: true,
      },
      firstRowData: [
        {
          name: "Document",
          price: "146.000",
          icon: "fa fa-fw fa-print",
          percentage: "17%",
          percentageIcon: "fa-solid fa-arrow-trend-up",
        },
        {
          name: "Contact",
          price: "1400",
          icon: "fa fa-fw fa-book",
          percentage: "17%",
          percentageIcon: "fa-solid fa-arrow-trend-up",
        },
        {
          name: "Email",
          price: "150.700",
          icon: "fa fa-fw fa-envelope",
          percentage: "17%",
          percentageIcon: "fa-solid fa-arrow-trend-up",
        },
      ],
      tableHeader: [
        {
          key: "name",
          name: "Name",
        },
        {
          key: "file",
          name: "File",
        },
        {
          key: "category",
          name: "Category",
        },
        {
          key: "author",
          name: "Author",
        },
        {
          key: "status",
          name: "Status",
        },
      ],
      tableData: [],
    };
  },
};
</script>
<style scoped>
.first-box-container {
  display: grid;
  grid-auto-flow: column;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 50px;
  margin-top: 20px;
}
.box-item {
  background-color: white;
  width: 230px;
  height: 200px;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
.space-between {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.margin-between {
  margin: 5px 0;
}
.box-price {
  font-weight: 900;
  font-size: 22px;
}
.box-title {
  font-weight: bold;
}
.box-text {
  font-size: 12px;
  font-weight: 200;
  color: gray;
}
.icon-background {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: lightblue;
  display: flex;
  align-items: center;
  justify-content: center;
  color: rgb(6, 162, 197);
}
.second-row-box-container {
  display: grid;
  grid-auto-flow: column;
  grid-template-columns: repeat(2, 1fr);
  gap: 10px;
  margin: 30px 0;
}
.second-row-box-item {
  background-color: white;
  width: 400px;
  height: 200px;
  border-radius: 10px;
  padding: 10px;
  display: flex;
  flex-direction: column;
}
.chart {
  width: 300px;
  height: 200px;
  object-fit: contain;
}
.third-box-container {
  display: grid;
  grid-auto-flow: column;
  grid-template-columns: auto;
}
.third-row-box-item {
  background-color: white;
  width: 850px;
  height: 300px;
  border-radius: 10px;
  padding: 10px;
}
th,
td {
  padding-top: 10px;
  padding-bottom: 20px;
  padding-left: 30px;
  padding-right: 40px;
  text-align: start;
}
.pending-btn {
  background-color: lightsalmon;
  color: red;
  border: 1px solid lightsalmon;
  border-radius: 4px;
  width: 100%;
  padding: 5px;
}
.send-btn {
  background-color: lightgreen;
  color: green;
  border: 1px solid lightgreen;
  border-radius: 4px;
  width: 100%;
  padding: 5px;
}
.time-period-drop-down {
  background-color: lightgray;
  color: black;
  width: 100px;
  padding: 8px;
  border: none;
  border-radius: 8px;
}
.table-content {
  margin: 10px 30px;
}
.green-color {
  color: green;
}
.bar-chart {
  height: 150px !important;
}
.line-chart {
  height: 150px !important;
}
</style>
