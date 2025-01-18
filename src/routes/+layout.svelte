<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<nav class="">
	<a href="/">Home</a>
	<a href="/counter">Counter</a>
	<a href="/temperature">Temperature</a>
	<a href="/flight">Flight</a>
</nav>

{@render children()}
