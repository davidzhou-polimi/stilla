<script lang="ts">
  import { onMount } from 'svelte';
  import TopBar from '$lib/components/TopBar.svelte';
  import Hero from '$lib/components/Hero.svelte';
  import Footer from '$lib/components/Footer.svelte';
  import Card from '$lib/components/Card.svelte';
  import FilterTab from '$lib/components/FilterTab.svelte';
  import { cards } from '$lib/data.js';

  // Caricamento dinamico delle immagini locali con Vite
  const images = import.meta.glob('$lib/assets/*.png', { eager: true, query: '?url', import: 'default' });

  // Precarica tutte le immagini nella cache del browser al mount
  onMount(() => {
    Object.values(images).forEach((url) => {
      const img = new Image();
      img.src = url as string;
    });
  });

  // Stato per il filtro attivo
  let selectedLevel = $state('Principiante');

  // Filtra le card in base al livello selezionato
  let filteredCards = $derived(cards.filter(card => card.level === selectedLevel));
</script>

<div class="min-h-screen w-full max-w-[1512px] mx-auto overflow-hidden bg-background-primary flex flex-col font-satoshi text-text-primary">
  <TopBar />
  
  <main class="flex-grow flex flex-col w-full">
    <Hero />
    
    <div class="flex flex-col w-full pb-10">
      <!-- Tab Navigation (Inline to easily manage state) -->
      <div id="filters-section" class="flex items-center justify-center md:justify-start gap-1 md:gap-2 px-6 md:px-10 lg:px-20">
        <FilterTab 
          selected={selectedLevel === 'Principiante'}
          onclick={() => selectedLevel = 'Principiante'}
        >
          Principiante
        </FilterTab>
        <FilterTab 
          selected={selectedLevel === 'Intermedio'}
          onclick={() => selectedLevel = 'Intermedio'}
        >
          Intermedio
        </FilterTab>
        <FilterTab 
          selected={selectedLevel === 'Avanzato'}
          onclick={() => selectedLevel = 'Avanzato'}
        >
          Avanzato
        </FilterTab>
      </div>
      
      <!-- Card Grid -->
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-6 px-6 md:px-10 lg:px-20 pt-4 pb-6 md:py-6">
        {#each filteredCards as card (card.title)}
          <Card 
            title={card.title} 
            level={card.level} 
            duration={card.duration} 
            image={images[`/src/lib/assets/${card.image}`]} 
          />
        {/each}
      </div>
    </div>
  </main>

  <Footer />
</div>
