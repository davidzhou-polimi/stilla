<script>
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';

    // Import custom tokens
    import "$lib/styles/tokens.css";

	let { children } = $props();
</script>

<svelte:head>
    <title>Stilla – Pratiche di meditazione e respirazione</title>
    <meta name="description" content="Meditazione, respirazione e mindfulness per ogni livello. Pratiche brevi e guidate per imparare a stare con se stessi – senza guru, senza app." />

    <link rel="icon" href={favicon} />

    <!-- Font Satoshi -->
    <link rel="preconnect" href="https://api.fontshare.com" />
    <link href="https://api.fontshare.com/v2/css?f[]=satoshi@400,500,700,900&display=swap" rel="stylesheet" />
</svelte:head>
{@render children()}
