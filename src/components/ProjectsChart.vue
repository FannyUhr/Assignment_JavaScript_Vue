<template>
  <div class="col-md-6 grid-margin stretch-card">
    <div class="card">
      <div class="card-body">
        <p class="card-title">Projects</p>
        <div class="d-flex flex-wrap align-items-baseline">
          <h2 class="mr-3">{{ projectChart.projects }}%</h2>
          <i class="mdi mdi-arrow-up mr-1 text-success"></i>
          <span><p class="mb-0 text-success font-weight-medium">{{ projectChart.growth }}%</p></span>                          
        </div>
        <p class="mb-0 text-muted">Total users world wide</p>
      </div>
      <canvas id="projects-chart"></canvas>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectsChart",
  data() {
    return {
      projectChart: String
    };
  },
  created() {
    fetch('https://inlupp-fa.azurewebsites.net/api/total-projects')
    .then(res => res.json())
    .then(data => {
      this.projectChart = data;
    });
  }
}
</script>