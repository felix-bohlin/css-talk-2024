<script setup>
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale
} from 'chart.js'
import { Bar } from 'vue-chartjs'

ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend)

const data = {
  labels: [
    "KILL IT WITH FIRE",
    "I avoid it if I can",
    "Ok I guess/I tolerate it",
    "I enjoy it!",
    "LET ME TELL YOU ABOUT subgrid!",
    "Rainbow animal emoji",
  ],
  datasets: [
    {
      label: "Respondents",
      backgroundColor: ["#dc2626", "#f97316", "#06b6d4", "#6366f1", "#a855f7", "#d946ef"],
      data: [1, 4, 9, 7, 5, 4],
      borderRadius: 4,
    }
  ]
}

const options = {
  responsive: true,
  maintainAspectRatio: false,
  plugins: {
    legend: {
      display: false,
    }
  }
}

</script>

<template>
  <Bar :data="data" :options="options" />
</template>
