<script lang="ts">
    let text: string = '';

    interface SaveResponse {
        message: string;
    }

    async function saveText(): Promise<void> {
        try {
            const response = await fetch('https://your-api-endpoint.com/save', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ text })
            });

            if (!response.ok) {
                throw new Error('Failed to save text');
            }

            const result: SaveResponse = await response.json();
            console.log('Server response:', result.message);
        } catch (error) {
            console.error('Error:', error);
        }
    }
</script>

<main>
    <input 
        type="text" 
        bind:value={text} 
        placeholder="Enter text here..." 
        class="big-input"
    />
    <button on:click={saveText} class="save-button">
        Save
    </button>
</main>

<style>
    main {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100vh;
        background-color: #f9fafb;
        flex-direction: column;
        gap: 1rem;
    }

    .big-input {
        width: 600px;
        height: 80px;
        font-size: 1.5rem;
        padding: 1rem;
        border: 2px solid #ccc;
        border-radius: 8px;
    }

    .save-button {
        background-color: #007BFF;
        color: white;
        padding: 1rem 2rem;
        font-size: 1.2rem;
        border: none;
        border-radius: 8px;
        cursor: pointer;
    }

    .save-button:hover {
        background-color: #0056b3;
    }
</style>
