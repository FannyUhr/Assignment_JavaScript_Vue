<template>
  <div class="col-xl-8 grid-margin stretch-card">
    <div class="card">
      <div class="card-body">
        <div class="d-flex justify-content-between align-items-md-end flex-wrap">
          <p class="card-title">Tickets</p>
        <div class="dropdown mb-3 mb-md-0">
        <button class="btn btn-sm btn-outline-light dropdown-toggle text-dark" type="button" id="dropdownMenuDate1" data-toggle="dropdown" aria-haspopup="true" aria-expanded="true">
          {{ selectedTicketsYear.year }}
        </button>
        <div class="dropdown-menu dropdown-menu-right" aria-labelledby="dropdownMenuDate1">
          <a v-on:click="selectedTicketsYear = ticketsYear" :key="ticketsYear.year" v-for="ticketsYear of tickets" class="dropdown-item" href="#">{{ ticketsYear.year }}</a>
        </div>
      </div>
    </div>
    <div class="table-responsive">
      <table class="table tickets-table mb-2">
        <thead>
          <th class="text-muted pl-0">
            Name
          </th>
          <th></th>
          <th class="text-muted">
            Date
          </th>
          <th class="text-muted">
            Projects
          </th>
            </thead>
            <tbody>
              <Ticket :key="ticket.name" v-for="ticket of selectedTicketsYear.tickets" :ticket="ticket"/>
            
            </tbody>
          </table>
        </div>
      </div>  
    </div>
  </div>
</template>

<script>
import Ticket from './Ticket'

export default {
  name: "Tickets",
  components: {
    Ticket
  },
  data() {
    return {
      tickets: [],
      selectedTicketsYear: Object
    };
  },
  created() {
    fetch("https://inlupp-fa.azurewebsites.net/api/tickets")
      .then(res => res.json())
      .then(data => {
        this.tickets = data;
        this.selectedTicketsYear = data[data.length - 1];
    });
  }
}
</script>