<script>
import {Line,mixins} from 'vue-chartjs';

export default {
  extends:Line,
  mixins: [Line],
  props: {
    label: {
      type: String
    },
    chartData: {
      type: Array
    },
    options: {
      type: Object
    }


  },
  mounted(){
    const noms = this.chartData.map(d => d.nom).reverse();
    const nums = this.chartData.map(d => d.num).reverse();

   /* this.renderChart({
      labels: noms,
      datasets: [{
        label: this.label,
        data: nums}]
    },
    this.options
    );*/
  }
}
</script>