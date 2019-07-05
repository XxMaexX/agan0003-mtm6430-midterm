<template>
  <div class="contact">
       <h1>Contact Us</h1>
    <div class="container">
    <div class="contact-container">
      <!-- first column, information about location -->
      <div class="location">
        <h2>Address</h2>
        <p>{{ address1 }}<br>{{ address2 }}<br>{{ phoneNumber }}</p>
      </div>
      <!-- second colum, information about hours -->
      <div class="hour" >
        <h2>Hours of operation</h2>
      <div class="hoursOperation">
        <ul>
          <li v-for="operation in hoursOpperation">{{ operation.day }}: {{ operation.hours }}</li>
        </ul>
      </div>
      </div>
    </div>
  </div>
    </div>
</template>

<script>
export default {
  data () {
    return {
   // returning text in required area
      address1: "1685 Woodroffe Avenue,",
      address2: "Ottawa, Ontario. K2G1V8",
      phoneNumber: "613-727-423",
      hoursOpperation: [
        {day: "Monday", hours: "8AM - 6PM"},
        {day: "Tuesday", hours: "8AM - 6PM"},
        {day: "Wednesday", hours: "8AM - 6PM"},
        {day: "Thursday", hours: "8AM - 6PM"},
        {day: "Friday", hours: "8AM - 5PM"},
        {day: "Saturday", hours: "10AM - 4PM"},
        {day: "Sunday", hours: "10AM - 2PM"}
      ]
    }
  }
}
</script>



<style>
  .container {
    padding-left: 0px;
  }

  .contact {
    max-width: 800px;
    margin: auto;
    text-align: left;
    padding-top: 100px;
  }

  .contact-container {
    display: flex;
  }

  h2 {
    text-decoration: underline;
    padding-bottom: 15px;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }

  .hoursOperation {
    display: felx;
    justify-content: center;
  }

  .location {
    padding-right: 90px; 
  }

  .hour {
    padding-left: 90px;
  }
</style>
