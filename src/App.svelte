<script>
	import PersonNr from "./components/PersonNr.svelte";
	import Form from "./components/Form.svelte";
	export let name;
</script>

<style lang="scss">
	:global(body){
		background-color: #f5f5f5;
		padding: 0;
		// color: #008737;
		
	}
	.main-content-wrapper {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		
		@media (min-width: 700px) {
			width: 80%;
   			margin: 0 auto;
			justify-content: flex-start;
			background-color: white;
			height: 100%;
		}

		header{
			background-color: white;
			width: 100%;
    		text-align: center;
		}
	}

	// h1 {
	// 	color: #ff3e00;
	// 	text-transform: uppercase;
	// 	font-size: 4em;
	// 	font-weight: 100;
	// }

	// @media (min-width: 640px) {
	// 	main {
	// 		max-width: none;
	// 	}
	// }
</style>

<div class="main-content-wrapper">
	<header>
		<h1>Advea finans portal</h1>
	</header>
	<Form />
	<!-- <PersonNr/> -->
</div>

