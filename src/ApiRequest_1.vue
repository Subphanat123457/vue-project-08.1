<template>
    <div style="padding: 0px; margin: 0px ;">  
      <div class="border">
        <h1>COVID-19 One Week in Thiland</h1>
        <a v-for="item in covidData_1" :key="item">
            <p>Province: {{ item.province }}</p>
            <p>New Case: {{ item.new_case }}
                Total Case: {{ item.total_case }}</p>  
            <a v-if="item.new_case > 0">
                <p style="color: red;">+{{ item.new_case }}</p>
            </a>
            <a v-else>
                <p style="color: green;">+0</p>
            </a>
        </a>
        
      </div>
    </div>
</template>

<script>
import axios from 'axios';
export default {
  data() {
    return { 
      covidData_1: []
    };
  },
    mounted() {
        
    axios
      .get("https://covid19.ddc.moph.go.th/api/Cases/today-cases-by-provinces")
        .then(response => {
        
          this.covidData_1 = response.data;
        console.log(this.covidData_1 = response.data);
        console.log(Object.keys(this.covidData_1).length);
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