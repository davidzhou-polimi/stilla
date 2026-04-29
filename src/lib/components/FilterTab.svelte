<script lang="ts">
  import type { Snippet } from 'svelte';

  let { selected = false, onclick, children } = $props<{
    selected?: boolean;
    onclick?: () => void;
    children?: Snippet;
  }>();
</script>

<!-- Rimuoviamo gap e usiamo px-4 per assecondare le varie lunghezze dei testi.
     h-[48px] forza l'altezza dell'SVG di Figma. -->
<button 
  {onclick}
  class="relative flex items-center justify-center px-4 h-[38px] md:h-[48px] text-h2 text-text-primary transition-colors duration-300 cursor-pointer group shrink-0"
>
  <!-- Background SVG Squircle.
       Utilizziamo viewBox allargata (-1 -1 159 50) per evitare il clipping del bordo (outline).
       - Default: squircle base visibile (nessun bordo)
       - Hover: aggiunge l'outline
       - Selected: aggiunge un outline scuro e/o riempimento diverso (in attesa di conferma)
  -->
  <svg 
    class="absolute inset-0 w-full h-full" 
    preserveAspectRatio="none" 
    xmlns="http://www.w3.org/2000/svg" 
    width="157" height="48" viewBox="-1 -1 159 50" fill="none"
  >
    <defs>
      <linearGradient id="paint0_linear_72_1218" x1="78.5" y1="0" x2="78.5" y2="48" gradientUnits="userSpaceOnUse">
        <stop stop-color="#EEEEEC" stop-opacity="0.25"/>
        <stop offset="0.2" stop-color="#EEEEEC"/>
      </linearGradient>
    </defs>
    
    <!-- Path per l'Outline (Stato Hover) -->
    <path 
      d="M0 24C0 4.236 4.236 0 24 0H133C152.764 0 157 4.236 157 24C157 43.764 152.764 48 133 48H24C4.236 48 0 43.764 0 24Z" 
      fill="none"
      class="transition-all duration-300 stroke-[1.5px] {!selected ? 'stroke-transparent group-hover:stroke-[#E6E6E6] group-active:stroke-[#E6E6E6]' : 'stroke-transparent'}"
    />
    
    <!-- Path per lo Sfondo (Stato Selected) animata in opacità -->
    <path 
      d="M0 24C0 4.236 4.236 0 24 0H133C152.764 0 157 4.236 157 24C157 43.764 152.764 48 133 48H24C4.236 48 0 43.764 0 24Z" 
      fill="url(#paint0_linear_72_1218)"
      class="transition-opacity duration-300 {selected ? 'opacity-100' : 'opacity-0'}"
    />
  </svg>
  
  <div class="relative z-10">
    {@render children?.()}
  </div>
</button>
