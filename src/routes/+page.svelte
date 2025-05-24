<script lang="ts">
	import { goto } from "$app/navigation";

	let text = $state('');

	function saveText(): void {
		if (text.trim() === '') {
			alert("Input can't be empty!");
			return;
		}
		console.log(text);
	}

    function gotoLogin(): void {
        goto("/login")
    }
</script>

<main>
	<input type="text" bind:value={text} placeholder="Enter text here..." class="big-input" />
	<button onclick={saveText} class="save-button"> Save </button>
    <button onclick = {gotoLogin} class="login-button"> Login </button>
</main>

<style>
	.big-input {
		width: 600px;
		height: 80px;
		font-size: 1.5rem;
		padding: 1rem;
		border: 2px solid #ccc;
		border-radius: 8px;
	}

	.save-button {
		background-color: #007bff;
	}

    .login-button {
        background-color: blueviolet;
    }

	.save-button:hover {
		background-color: #0056b3;
	}
</style>
