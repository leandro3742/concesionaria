<script>
	export let segment;
</script>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Anton&display=swap');
	a{
		font-family: 'Anton', sans-serif;
	}
	.header{
		display: flex;
		justify-content: center;
	}
	
	nav {
		border-bottom: 1px solid rgba(255,62,0,0.1);
		font-weight: 300;
		padding: 0 1em;
	}

	ul {
		display: grid;
		grid-template-columns: 1fr 1fr;
		max-width: 70%;
		margin-left: 15%;
		padding: 0;
		background: #2b6cb0;
		border-radius: 20px;
	}

	/* clearfix */
	ul::after {
		content: '';
		display: block;
		clear: both;
	}

	li {
		display: flex;
		justify-content: center;
		/* display: block;
		float: left; */
	}

	[aria-current] {
		position: relative;
		display: inline-block;
	}

	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		background-color: rgb(255,62,0);
		display: block;
		bottom: -1px;
	}

	a {
		text-decoration: none;
		padding: 1em 0.5em;
		display: block;
		color: white;
		font-style: oblique;
		font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
	}

	@media screen and (min-width: 600px){
       a{
           font-size: 25px;
	   }
	}
</style>

<nav>
	<div class="header">
		<img class="logo" src=logo.png alt="logo" />
	</div>
	<ul>
		<li><a aria-current="{segment === undefined ? 'page' : undefined}" href=".">Home</a></li>
		<li><a aria-current="{segment === 'about' ? 'page' : undefined}" href="about">Contactanos</a></li>

	</ul>
</nav>
