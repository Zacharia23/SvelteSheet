<script lang="ts">
	import { Label } from 'bits-ui';
	import { Button } from '$lib/components/ui/button';

	type Options = "One-way" | "Return";

	function handleSubmit(e: Event) {
		e.preventDefault()
		alert(`You have booked a flight ${selected} on ${startDate}`)
	}

	let selected = $state<Options>('One-way')
	let startDate = $state()
	let returnDate = $state()
</script>

<form onsubmit={handleSubmit} class="grid grid-cols-3 gap-y-2 gap-x-2">

	<select bind:value={selected}>
		<option value="One-way">One-way flight</option>
		<option value="Return">Return flight</option>
	</select>

	<label>
		<span>Select the start date</span>
		<input type="date" bind:value={startDate} />
	</label>

	<label>
		<span>Select the return date</span>
		<input type="date" bind:value={returnDate} />
	</label>

	<Button type="submit">Submit
		Book Now
	</Button>
</form>
