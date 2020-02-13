<script>
	export let name;
	import Asyncer from "./Asyncer.svelte"
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<h1>Hello {name}!</h1>
<Asyncer/>