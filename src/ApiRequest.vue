<template>
<div style="padding: 0px; margin: 0px ;">  
    
      <div class="border">
        <h1>COVID-19 One Week in Thiland</h1>
        <p>Confirmed Cases: {{ covidData.year }}</p>
        <p>New Case: {{ covidData.new_case }}</p>
        <p>Total Case: {{ covidData.total_case }}</p>
        <p>New Deaths: {{ covidData.new_death }}</p>
        <p>Total Deaths: {{ covidData.total_death }}</p>
        <p>Last Update: {{ covidData.update_date }}</p>
        
      </div>
        <selectitem />
    </div>
    
  
</template>
<script>
import selectitem from './select.vue';
import axios from 'axios';
export default {
  components: {
    selectitem
  },
  data() {
    return { 
      covidData: {}
    };
  },
  mounted() {
    axios
      .get("https://covid19.ddc.moph.go.th/api/Cases/today-cases-all")
      .then(response => {
        this.covidData = response.data[0];
        console.log(this.covidData = response.data[0]);
        console.log(Object.keys(this.covidData).length);
      })
      .catch(error => {
        console.error(error);
        this.errorMessage = "An error occurred while retrieving COVID-19 data. Please try again later.";
    });
  }
  
};

</script>

<style>

</style>