<template>
<div >  
  <navbar />
  <div class="app">
  <api-request />
  <api-request_1 />
  
</div>
  </div>
</template>
<script>
import Navbar from './components/nevbar.vue';
import ApiRequest from './components/ApiRequest.vue';
import ApiRequest_1 from './components/ApiRequest_1.vue';

export default {
  components: {
    Navbar,
    ApiRequest,
    ApiRequest_1,
  }
};

</script>

<style>

</style>