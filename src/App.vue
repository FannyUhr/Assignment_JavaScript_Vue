<template>
  <div class="container-scroller">
    <div class="horizontal-menu">
      <nav class="navbar top-navbar col-lg-12 col-12 p-0">
        <div class="container">
          <div class="navbar-menu-wrapper d-flex align-items-center">
            <ul class="navbar-nav navbar-nav-right">

              <Messages />
              <Notifications />
              <MainUsers :text="userName" />

            </ul>
            <button class="navbar-toggler navbar-toggler-right d-lg-none align-self-center" type="button" data-toggle="horizontal-menu-toggle">
              <span class="mdi mdi-menu"></span>
            </button>
          </div>
        </div>
      </nav>
    </div>

    <div class="container-fluid page-body-wrapper">
      <div class="main-panel">
        <div class="content-wrapper">

          <Welcome :text="userName" />

          <div class="row">
            <div class="col-xl-6 grid-margin">
              <div class="row">

                <TotalUsersChart />
                <ProjectsChart />

              </div>
              <div class="row">
                
                <DownloadsChart />

              </div>
            </div>

            <TotalSalesChart />
            
          </div>

          <div class="row">

            <TotalSales />            
            <TotalPurchases />
            <TotalOrders />
            <TotalGrowth />

          </div>

          <div class="row">
            
            <Tickets />           
            <Updates />

          </div>

          <div class="row">

            <Distribution />
            <SalesReportCard />

          </div>

          <div class="row">
            <div class="col-md-12">

              <OpenInvoices />

            </div>
          </div>
        </div>
        
        <Footer />

      </div>
    </div>
  </div>
</template>

<script>
import Messages from "./components/messages/Messages"
import Notifications from "./components/notifications/Notifications"
import MainUsers from "./components/main_users/MainUsers"
import Welcome from "./components/Welcome"
import TotalUsersChart from "./components/TotalUsersChart"
import ProjectsChart from "./components/ProjectsChart"
import DownloadsChart from "./components/DownloadsChart"
import TotalSalesChart from "./components/TotalSalesChart"
import TotalSales from "./components/totals/TotalSales"
import TotalPurchases from "./components/totals/TotalPurchases"
import TotalOrders from "./components/totals/TotalOrders"
import TotalGrowth from "./components/totals/TotalGrowth"
import Tickets from "./components/tickets/Tickets"
import Updates from "./components/updates/Updates"
import Distribution from "./components/Distribution"
import SalesReportCard from "./components/sales_report/SalesReportCard"
import OpenInvoices from "./components/open_invoices/OpenInvoices"
import Footer from "./components/Footer"

export default {
  name: "app",
  components: {
    Messages,
    Notifications,
    MainUsers,
    Welcome,
    TotalUsersChart,
    ProjectsChart,
    DownloadsChart,
    TotalSalesChart,
    TotalSales,
    TotalPurchases,
    TotalOrders,
    TotalGrowth,
    Tickets,
    Updates,
    Distribution,
    SalesReportCard,
    OpenInvoices,
    Footer
  },
  data() {
      return {
        userName: String
      }   
    },
  created() {
    fetch("https://inlupp-fa.azurewebsites.net/api/users?firstname=Don&lastname=Richards").then(res => res.text())
    .then(data => {
      this.userName = `${data}`;
    })
  }
};
</script>