<script>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

    // Import custom tokens
    import "$lib/styles/tokens.css";

	let { children } = $props();
</script>

<svelte:head>
    <link rel="icon" href={favicon} />

    <!-- Font Satoshi -->
    <link rel="preconnect" href="https://api.fontshare.com" />
    <link href="https://api.fontshare.com/v2/css?f[]=satoshi@1,2&display=swap" rel="stylesheet" />
</svelte:head>
{@render children()}
