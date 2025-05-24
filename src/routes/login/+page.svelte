<script lang="ts">
	let username = $state('');
	let password = $state('');

	function printCredentials(): void {
		if (username.trim() === '') {
			alert("Username can't be empty!");
			return;
		} else if (password.trim() === '') {
			alert("Password can't be empty!");
			return;
		} else {
			console.log(`Username: ${username}\nPassword: ${password}`)
		}
	}
</script>

<main>
	<div class="title">LOGIN PAGE</div>
	<div class="container-input">
		<input type="text" bind:value={username} placeholder="Username" class="big-input" />
		<input type="text" bind:value={password} placeholder="Password" class="big-input" />
	</div>
	<div class="container-buttons">
		<button class="btn-login" onclick={printCredentials}> Login </button>
		<button class="btn-register"> Register </button>
	</div>
</main>

<style>
	main {
		display: flex;
		align-items: center;
		justify-content: center;
		flex-direction: column;
		height: 100vh;
		gap: 1rem;
	}

	.container-input {
		display: flex;
		flex-direction: column;
		margin-bottom: 2rem;
		gap: 1rem;
	}

	.container-buttons {
		display: flex;
		gap: 1rem;
	}

	.btn-login {
		background-color: green;
	}

	.btn-register {
		background-color: yellowgreen;
	}

	.title {
		font-size: 2rem;
		padding-bottom: 4rem;
	}
</style>
