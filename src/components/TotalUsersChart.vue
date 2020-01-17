<template>
  <div class="col-md-6 grid-margin stretch-card">
    <div class="card">
      <div class="card-body">
        <p class="card-title">Users</p>
        <div class="d-flex flex-wrap align-items-baseline">
          <h2 class="mr-3">{{ usersChart.users }}</h2>
          <i class="mdi mdi-arrow-up mr-1 text-danger"></i>
          <span><p class="mb-0 text-danger font-weight-medium">{{ usersChart.growth }}%</p></span>
        </div>
        <p class="mb-0 text-muted">Total users world wide</p>
      </div>
      <canvas id="users-chart"></canvas>
    </div>
  </div>
</template>

<script>
export default {
  name: "TotalUsersChart",
  data() {
    return {
      usersChart: String
    };
  },
  created() {
    fetch('https://inlupp-fa.azurewebsites.net/api/total-users')
    .then(res => res.json())
    .then(data => {
      this.usersChart = data;
    });
  }
}
</script>