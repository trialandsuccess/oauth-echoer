<script>
    const hash_settings = Object.fromEntries(new URLSearchParams(window.location.hash))
    const search_settings = Object.fromEntries(new URLSearchParams(window.location.search))

    const settings = {...hash_settings, ...search_settings};

    const token = settings.access_token
</script>

<style>
    main {
        text-align: center;
        padding: 1em;
        max-width: 240px;
        margin: 0 auto;
    }

    h1 {
        color: #ff3e00;
        text-transform: uppercase;
        font-size: 4em;
        font-weight: 100;
    }

    @media (min-width: 640px) {
        main {
            max-width: none;
        }
    }
</style>

<main>
    {#if token}
        <p>{token}</p>
    {:else}
		<p>Welcome to oauth echoer. This webpage simply echoes oauth access tokens.</p>
    {/if}
</main>

