<script>
	import ContactCard from './ContactCard.svelte';
	import Goal from './Goal.svelte';

	let name = 'Max';
	let age = 30;
	let image = '';
	let jobName = 'System Engineer';
	let description = 'Since 08.Oct.2022, working as a System Engineer in Tokyo';
	let goal = '';

	$: uppercaseName = name.toUpperCase();
	$: console.log(name);
	$: if (name === 'chanho') {
		age = 26;
	}

	function incrementAge() {
		age += 1;
	}
	function changeName() {
		name = 'chanho';
	}
	function nameInput(event) {
		const enteredValue = event.target.value;
		name = enteredValue;
	}
</script>

<h1>Hello {uppercaseName}, my age is {age}!</h1>
<button on:click={incrementAge}>Change Age</button>
<!-- <button on:click={changeName}>Change Name</button> -->
<!-- <input type="text" on:input={nameInput} value={name} /> -->
<input type="text" bind:value={name} />
<input type="text" bind:value={jobName} />
<input type="text" bind:value={image} />
<textarea bind:value={description} />

<input type="text" bind:value={goal} />

<ContactCard userName={name} {jobName} {description} userImage={image} />

<Goal {goal} />

<style>
	h1 {
		color: purple;
	}
</style>
