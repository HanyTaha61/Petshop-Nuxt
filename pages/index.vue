<template>
<div class="main">
	<navBar/>
	<navBar2/>
	<nuxt />
</div>
</template>

<script>
import navBar from '../components/navbar';
import navBar2 from '../components/navbar2';

export default {
	components:{navBar, navBar2},
	head(){
		return{
			
		}
	}
}
</script>

<style>
@import url('https://use.fontawesome.com/releases/v5.11.2/css/all.css');
@import url('https://fonts.googleapis.com/css?family=Josefin+Sans&display=swap');
@import url('https://fonts.googleapis.com/css?family=Liu+Jian+Mao+Cao&display=swap');

:root{
  --primary-color: #f5c22b;
  --secondary-color:#368ac5;
  --third-color:#e2393f;
}
</style>
