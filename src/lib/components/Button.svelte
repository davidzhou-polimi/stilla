<script lang="ts">
  import type { Snippet } from 'svelte';

  let { onclick, children, class: className = '' } = $props<{
    onclick?: (event: MouseEvent) => void;
    children?: Snippet;
    class?: string;
  }>();
</script>

<button 
  {onclick}
  class="relative flex items-center justify-center w-[209px] h-[46px] md:w-[281px] md:h-[64px] text-h2 text-text-primary cursor-pointer group {className}">
  
  <!-- Desktop SVG Background (Default) -->
  <svg class="absolute inset-0 w-full h-full transition-opacity duration-1000 opacity-100 group-hover:opacity-0 hidden lg:block" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="281" height="64" viewBox="0 0 281 64" fill="none">
    <path d="M32 0.400391H249C255.579 0.400391 260.838 0.752916 265.03 1.68457C269.218 2.61525 272.317 4.11771 274.6 6.40039C276.882 8.68307 278.385 11.782 279.315 15.9697C280.247 20.1619 280.6 25.4212 280.6 32C280.6 38.5788 280.247 43.8381 279.315 48.0303C278.385 52.218 276.882 55.3169 274.6 57.5996C272.317 59.8823 269.218 61.3847 265.03 62.3154C260.838 63.2471 255.579 63.5996 249 63.5996H32C25.4212 63.5996 20.1619 63.2471 15.9697 62.3154C11.782 61.3847 8.68307 59.8823 6.40039 57.5996C4.11771 55.3169 2.61525 52.218 1.68457 48.0303C0.752916 43.8381 0.400391 38.5788 0.400391 32C0.400391 25.4212 0.752916 20.1619 1.68457 15.9697C2.61525 11.782 4.11771 8.68307 6.40039 6.40039C8.68307 4.11771 11.782 2.61525 15.9697 1.68457C20.1619 0.752916 25.4212 0.400391 32 0.400391Z" fill="white" stroke="#D4D4D4" stroke-width="0.8"/>
  </svg>

  <!-- Tablet SVG Background (Default) -->
  <svg class="absolute inset-0 w-full h-full transition-opacity duration-1000 opacity-100 group-hover:opacity-0 hidden md:block lg:hidden" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="281" height="64" viewBox="0 0 281 64" fill="none">
    <path d="M32 0.400391H249C255.579 0.400391 260.838 0.752916 265.03 1.68457C269.218 2.61525 272.317 4.11771 274.6 6.40039C276.882 8.68307 278.385 11.782 279.315 15.9697C280.247 20.1619 280.6 25.4212 280.6 32C280.6 38.5788 280.247 43.8381 279.315 48.0303C278.385 52.218 276.882 55.3169 274.6 57.5996C272.317 59.8823 269.218 61.3847 265.03 62.3154C260.838 63.2471 255.579 63.5996 249 63.5996H32C25.4212 63.5996 20.1619 63.2471 15.9697 62.3154C11.782 61.3847 8.68307 59.8823 6.40039 57.5996C4.11771 55.3169 2.61525 52.218 1.68457 48.0303C0.752916 43.8381 0.400391 38.5788 0.400391 32C0.400391 25.4212 0.752916 20.1619 1.68457 15.9697C2.61525 11.782 4.11771 8.68307 6.40039 6.40039C8.68307 4.11771 11.782 2.61525 15.9697 1.68457C20.1619 0.752916 25.4212 0.400391 32 0.400391Z" fill="white" stroke="#D4D4D4" stroke-width="0.8"/>
  </svg>

  <!-- Mobile SVG Background (Default) -->
  <svg class="absolute inset-0 w-full h-full transition-opacity duration-1000 opacity-100 group-hover:opacity-0 block md:hidden" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="209" height="46" viewBox="0 0 209 46" fill="none">
    <path d="M23 0.400391H186C190.726 0.400391 194.496 0.65343 197.497 1.32031C200.494 1.98627 202.699 3.05879 204.32 4.67969C205.941 6.30059 207.014 8.5064 207.68 11.5029C208.347 14.5039 208.6 18.2743 208.6 23C208.6 27.7257 208.347 31.4961 207.68 34.4971C207.014 37.4936 205.941 39.6994 204.32 41.3203C202.699 42.9412 200.494 44.0137 197.497 44.6797C194.496 45.3466 190.726 45.5996 186 45.5996H23C18.2743 45.5996 14.5039 45.3466 11.5029 44.6797C8.5064 44.0137 6.30059 42.9412 4.67969 41.3203C3.05879 39.6994 1.98627 37.4936 1.32031 34.4971C0.65343 31.4961 0.400391 27.7257 0.400391 23C0.400391 18.2743 0.65343 14.5039 1.32031 11.5029C1.98627 8.5064 3.05879 6.30059 4.67969 4.67969C6.30059 3.05879 8.5064 1.98627 11.5029 1.32031C14.5039 0.65343 18.2743 0.400391 23 0.400391Z" fill="white" stroke="#D4D4D4" stroke-width="0.8"/>
  </svg>

  <!-- Hover SVG Background (Fornito dall'utente) -->
  <svg class="absolute inset-0 w-full h-full transition-opacity duration-1000 opacity-0 group-hover:opacity-100" preserveAspectRatio="none" xmlns="http://www.w3.org/2000/svg" width="281" height="64" viewBox="0 0 281 64" fill="none">
    <path d="M0 32C0 5.648 5.648 0 32 0H249C275.352 0 281 5.648 281 32C281 58.352 275.352 64 249 64H32C5.648 64 0 58.352 0 32Z" fill="url(#paint0_linear_112_2151)"/>
    <defs>
      <linearGradient id="paint0_linear_112_2151" x1="140.5" y1="0" x2="140.5" y2="64" gradientUnits="userSpaceOnUse">
        <stop stop-color="#E8FCFD" stop-opacity="0.5"/>
        <stop offset="0.2" stop-color="#E8FCFD"/>
        <stop offset="1" stop-color="#D1F8FD"/>
      </linearGradient>
    </defs>
  </svg>

  <!-- Contenuto testuale -->
  <div class="relative z-10">
    {@render children?.()}
  </div>
</button>
