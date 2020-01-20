<template>
<div>
	<h1>Workout Companion</h1>
	<h2 class="acce2">Geoffrey Schofield</h2>

  <div class="description">
    <p> 
    Welcome to Workout Companion. Stay active and Sweat!
    </p>

    <ul>
      <li><router-link :to="{name:'requests', params:{} }">See exercises</router-link></li>
      <li><router-link :to="{name:'requests', params:{} }">Workout</router-link></li>
      <li><router-link :to="{name:'requests', params:{} }">Track Weight</router-link></li>
    </ul>
  </div>
  
	<table class="table table-striped">
    <thead>
      <tr>
      	<th>Type</th>
        <th>Details</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="reqq in requests">
      	<td>{{reqq.device_type}}</td>
        <td><router-link :to="{name:'detail', params:{ id:reqq.id } }">{{reqq.details}}</router-link></td>
      </tr>
    </tbody>
  </table>
</div>
</template>
<script>
import BackEndWrapper from '../services/BackEndWrapper';
export default {
  name: 'Requests',
  data(){
  	return ({
  		bw:new BackEndWrapper(),
  		requests:[]
  	});
  },
  mounted()
  {
      this.loadRequests();
  },
  methods:
  {
  	loadRequests()
  	{
	  	this.bw.loadRequests().then(function(res)
	  	{
        console.log('requests ', res);
	  		this.requests = res;
	  	}.bind(this), 
	  	function(err)
        {
          //this.showError();

        }.bind(this));	
  	}
  	
  }
}
</script>