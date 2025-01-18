<script lang="ts">
	import { Input } from '$lib/components/ui/input';
	import { Button } from '$lib/components/ui/button';

	let counter = $state(0)
</script>

<div class='w-[500px]'>
	<Input type="text" bind:value={counter} />
	<Button onclick={() => counter++}>Counter</Button>
</div>