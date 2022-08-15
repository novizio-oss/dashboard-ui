<script>
import { Line, mixins } from 'vue-chartjs'
const { reactiveProp } = mixins

export default {
    name: 'LineGraph',
    extends: Line,
    mixins: [reactiveProp],
    props: {
        chartData: {
            type: Object,
            default: null,
        },
        options: {
            type: Object,
            default: null,
        },
        width: {
            type: Number,
            default: 400
        },
        height: {
            type: Number,
            default: 400
        },
        plugins: {
            type: Object,
            default: () => {}
        }
    },
    mounted() {
        this.renderChart(this.chartData, this.options);
    }
}
</script>