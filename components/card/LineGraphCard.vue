<template>
    <div class="card">
        <div v-if="label" class="label">{{ label }}</div>
        <div v-if="text">{{ text }}</div>
        <div class="body">
          <LineGraph
            v-if="visible"
            :chart-data="chartData"
            :options="options"
            :width="r_width"
            :height="r_height"
          />
        </div>
    </div>
</template>

<script>
import LineGraph from '../graph/LineGraph.vue';
export default {
    name: "LineGraphCard",
    props: ["label", "text", "datasets", "labels", 'width', "height"],
    components: { LineGraph },
    data() {
      return {
        chartData: {
          labels: null,
          datasets: [],
        },
        options: {
          responsive: true,
          maintainAspectRatio: false,
        },
        r_width: 300,
        r_height: 200,
        visible: false,
      }
    },
    mounted() {
      const source = this.$props.datasets;
      const labels = this.$props.labels;

      // ラベルの設定 - X軸
      this.chartData.labels = labels;

      for (let key in source) {

        this.chartData.datasets.push({
          label: '売上',
          lineTension: 0,
          borderColor: '#ff0000',
          data: source[key],
        });
      }

      // イニシャライズ
      const prop_widht = this.$props.width;
      const prop_height = this.$props.height;

      if (prop_widht != undefined) {
        this.r_width = prop_widht;
      }
      if (prop_height != undefined) {
        this.r_height = prop_height;
      }

      this.visible = true;
    }
}
</script>

<style>
.card {
  width: 310px;
}
.card .label {
  font-size: 11px;
  color: #7f7f7f;
}
.card .body {
  width: 300px;
}
</style>