<script lang="ts">
  let { title, level, duration, image } = $props<{
    title: string;
    level: string;
    duration: string;
    image: string;
  }>();
</script>

<div class="flex flex-col gap-3 items-start relative w-full cursor-pointer group">
  <div class="w-full aspect-[664/400] relative overflow-hidden rounded-sm group-hover:rounded-xl transition-all duration-300 ease-out shrink-0">
    <div class="absolute inset-0 bg-background-secondary"></div>
    <img 
      src={image} 
      alt={title} 
      class="absolute inset-0 w-full h-full object-cover" 
    />
  </div>
  <div class="flex items-center w-full shrink-0">
    <div class="flex items-center gap-2 whitespace-nowrap flex-wrap">
      <p class="text-card-title text-text-primary">{title}</p>
      <span class="text-h2 text-text-secondary">/</span>
      <p class="text-h2 text-text-secondary">{level}</p>
      <span class="text-h2 text-text-secondary">/</span>
      <p class="text-h2 text-text-secondary">{duration}</p>
    </div>
  </div>
</div>
