<template>
	<div class="wrapper" id="req_app" >
		<!-- Sidebar  -->
		<nav id="sidebar" v-class="{active:isActive}">
		    <div class="sidebar-header">
		        <h3>Workout Companion</h3>XXX
		    </div>
		    <ul class="list-unstyled components">
				<li><router-link to="/"> Home</router-link></li>
		        <li><router-link to="/requests"> Exercises</router-link></li>
		        <li><router-link to="/requests"> Workout</router-link></li>
		        <li><router-link to="/requests"> Requests</router-link></li>
		        <li><router-link to="/requests"> Weight</router-link></li>
		    	<li><router-link to="/requests"> Contact me</router-link></li>
		        <li><router-link to="/approved"> Approved Requests</router-link></li>
		        <li><router-link to="/new"> New Request</router-link></li>
		    </ul>
		</nav>


		<!-- Toggle button -->


		<!-- Page Content  -->
		<div id="content">
			<div id="sidebarCollapseDiv">
				
				<button type="button" id="sidebarCollapse" class="btn btn-info"  @click="toggleSidebar()">
					<i class="fas fa-align-left"></i>
					<span>Toggle Sidebar</span>
				</button>
			</div>
			<router-view></router-view>
		</div>
	</div>
</template>
<script>

import router from './pages/routes';
export default {
  name: 'AppMain',
  router,

  data:{
	isActive: false
  },
  created(){
	  console.log("Created!")
  },
  methods:
  {
  	toggleSidebar()
  	{
		  console.log("Teest");
		  this.isActive = !this.isActive;

  	}
  }
}



</script>