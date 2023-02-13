<script lang="ts">
	import type { Snapshot } from './$types'

	let formData = {
		firstName: '',
		lastName: '',
		address: '',
		city: '',
		state: '',
		phone: ''
	}

	export const snapshot: Snapshot = {
		capture: () => formData,
		restore: (value) => (formData = value)
	}
</script>

<h1>SvelteKit Snapshots</h1>
<div class="center">
	<form method="POST">
		<div class="split-input">
			<div class="form-control">
				<label for="firstName">First Name</label>
				<input type="text" name="firstName" bind:value={formData.firstName} />
			</div>
			<div class="form-control">
				<label for="lastName">Last Name</label>
				<input type="text" name="lastName" bind:value={formData.lastName} />
			</div>
		</div>
		<div class="form-control">
			<label for="address">Address</label>
			<input type="text" name="address" bind:value={formData.address} />
		</div>
		<div class="form-control">
			<label for="phone">Phone</label>
			<input type="text" name="phone" bind:value={formData.phone} />
		</div>
		<div class="split-input">
			<div class="form-control">
				<label for="city">City</label>
				<input type="text" name="city" bind:value={formData.city} />
			</div>
			<div class="form-control">
				<label for="state">State</label>
				<input type="text" name="state" bind:value={formData.state} />
			</div>
		</div>
		<button>Submit</button>
		<p>
			By signing up, you agree to our <a href="/terms">Terms and conditions</a>
		</p>
	</form>
</div>
