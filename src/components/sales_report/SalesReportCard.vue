<template>
  <div class="col-xl-9 grid-margin stretch-card">
    <div class="card">
      <div class="row">
        
        <SalesReportChart />

        <SalesReportOverview />
        
      </div>
    </div>
  </div>
</template>

<script>
import SalesReportChart from "./SalesReportChart"
import SalesReportOverview from "./SalesReportOverview"

export default {
  name: "SalesReportCard",
  components: {
      SalesReportChart,
      SalesReportOverview
  },
}
</script>