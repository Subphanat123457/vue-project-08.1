<template>
  <div class="container-fluid">
  <div class="row">
    <div class="col-md-6">
      <div class="card">
        <div class="card-body">
          <canvas id="chartBar"></canvas>
        </div>
      </div>
    </div>
  </div>
</div>
</template>

<script>
 const ctx = document.getElementById("chart").getContext('2d');
      const myChart = new Chart(ctx, {
        type: 'doughnut',
        data: {
          labels: ["rice", "yam", "tomato", "potato", "beans",
           "maize", "oil"],
          datasets: [{
            label: 'food Items',
            data: [30, 40, 20, 50, 80, 90, 20],
            backgroundColor: ["#0074D9", "#FF4136", "#2ECC40",
            "#FF851B", "#7FDBFF", "#B10DC9", "#FFDC00",
            "#001f3f", "#39CCCC", "#01FF70", "#85144b",
            "#F012BE", "#3D9970", "#111111", "#AAAAAA"]
          }]
        },
      });
export default {


}

</script>

<style>

</style>