<template>
  <div id="overview">
    <h2>今日</h2>
    <div class="shop-list">

      <LineGraphCard
        label="総売上-○○店"
        text="￥3,000"
        :datasets="{
          '高木店': [2000, 5000, 4500, 8000],
        }"
        :labels="['8/9', '8/10', '8/11', '8/12']"
      />
      <LineGraphCard
        label="総売上-○○店"
        text="￥3,000"
        :datasets="{
          '高木店': [2000, 5000, 4500, 8000],
        }"
        :labels="['8/9', '8/10', '8/11', '8/12']"
      />

    </div>
  </div>
</template>

<style>
h3, h4 {
  margin-bottom: 12px;
}
.shop-list {
  width: 100%;
  display: flex;
}
</style>

<script>
import LineGraph from "../components/graph/LineGraph.vue"
import LineGraphCard from "../components/card/LineGraphCard.vue";

export default {
    name: "IndexPage",
    layout: "default",
    components: { LineGraph, LineGraphCard },
    data() {
      return {
        chartData: {
          labels: ['8/9', '8/10', '8/11', '8/12'],
          datasets: [
            {
              label: '売上',
              lineTension: 0,
              borderColor: '#ff0000',
              data: [2000, 5000, 4500, 8000]
            }
          ]
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
        }
      }
    }
}
</script>
