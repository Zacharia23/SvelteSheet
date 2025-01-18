<script lang="ts">
	import { Input } from '$lib/components/ui/input/index.js';

	class Temperature {
		 #centigrade = $state(0) //private #
		 #farenheight = $state(0)

		get centigrade() {
			 return this.#centigrade
		}

		set centigrade(value) {
			 this.#centigrade = value;
			 this.#farenheight = value * (9 / 5) + 32;
		}

		get farenheight() {
			return this.#farenheight
		}

		set farenheight(value) {
			this.#farenheight = value;
			this.#centigrade = (value - 32) * (5 / 9);
		}
	}

	const temperature = new Temperature();
</script>

<div class="flex flex-row w-[40ch] items-center justify-center">
	<Input type="number" bind:value={temperature.centigrade}/> Celsius = <Input type="number" bind:value={temperature.farenheight}/> Fahrenheit
</div>