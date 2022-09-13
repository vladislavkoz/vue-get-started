<template>
	<div id="nav">
		<router-link to="/">Home</router-link>
		|
		<router-link to="/about">About</router-link>
	</div>
	<router-view/>
</template>

<style lang="scss">
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
}

#nav {
	padding: 30px;
	
	a {
		font-weight: bold;
		color: #2c3e50;
		
		&.router-link-exact-active {
			color: #42b983;
		}
	}
}

button {
	margin-bottom: 2rem;
	appearance: none;
	background-color: #2ea44f;
	border: 1px solid rgba(27, 31, 35, .15);
	border-radius: 6px;
	box-shadow: rgba(27, 31, 35, .1) 0 1px 0;
	box-sizing: border-box;
	color: #fff;
	cursor: pointer;
	display: inline-block;
	font-family: -apple-system, system-ui, "Segoe UI", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji";
	font-size: 14px;
	font-weight: 600;
	line-height: 20px;
	padding: 6px 16px;
	position: relative;
	text-align: center;
	text-decoration: none;
	user-select: none;
	-webkit-user-select: none;
	touch-action: manipulation;
	vertical-align: middle;
	white-space: nowrap;
}
</style>
