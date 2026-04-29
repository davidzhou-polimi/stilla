<script lang="ts">
  import Button from './Button.svelte';

  function scrollToFilters() {
    const filters = document.getElementById('filters-section');
    if (filters) {
      // 24px di offset, corrispondente al padding `py-6` che separa filtri e griglia
      const offset = 24; 
      const elementPosition = filters.getBoundingClientRect().top;
      const offsetPosition = elementPosition + window.scrollY - offset;
      
      window.scrollTo({
        top: offsetPosition,
        behavior: 'smooth'
      });
    }
  }
</script>

<div class="flex flex-col items-center justify-center pt-20 pb-30 px-6 md:px-10 lg:px-20 gap-10 relative w-full">
  <div class="text-center w-full max-w-[664px]">
    <h1 class="text-h1 text-text-primary">
      La testa non si ferma.<br />
      Un respiro alla volta,<br />
      impara a starci.
    </h1>
  </div>
  <p class="text-h2 text-text-primary text-center">
    Niente guru, niente app, solo tu.
  </p>
  
  <Button onclick={scrollToFilters}>
    Comincia a respirare
  </Button>
</div>
