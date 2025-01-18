<script lang="ts">
	import Header from './Header.svelte';
	let name = $state('HunterByte')

	let status: 'OPEN' | 'CLOSED' = $state('OPEN');
	let fullName = $derived(name + "" + "Tolinski")
	function toggle() {
		status = status === "OPEN" ? 'CLOSED' : 'OPEN';
	}
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
<Header {name} />

<h1>{fullName}</h1>
<input type="text" bind:value={name} />

<p>The Store is now {status}</p>
<button onclick={toggle}>Toggle Status</button>