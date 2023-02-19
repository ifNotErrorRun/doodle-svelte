<script>
	export let goal;
</script>

<h1 class:containExclamation={goal.includes('!')}>{goal}</h1>

<style>
	.containExclamation {
		color: red;
	}
</style>
